---
title: Visão geral da importação dos arquivos PST da sua organização
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
description: 'Para administradores: saiba mais sobre o serviço de importação no Centro de Conformidade e Segurança para importar dados de email (arquivos PST) em massa às caixas de correio de usuário no Exchange Online. Este tópico fornece perguntas frequentes e explica como funciona p processo de importação de PST.'
ms.openlocfilehash: baf8fc0dbfb464dcf6b8054a9d91aacda00e3da6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636624"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a>Visão geral da importação dos arquivos PST da sua organização

> [!NOTE]
> Este artigo é para administradores. Você está tentando importar arquivos PST para sua própria caixa de correio? Confira [Importar emails, contatos e calendário de um arquivo .pst do Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)

Você pode usar o serviço de importação no Centro de Conformidade e Segurança para importar arquivos PST em massa rapidamente para as caixas de correio do Exchange Online em sua organização. Há duas maneiras de importar arquivos PST para o Office 365:

- **Carregamento de rede** ![Carregamento de nuvem](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png) - Carrega os arquivos PST pela rede para um local temporário de Armazenamento do Azure na nuvem da Microsoft. Em seguida, use o serviço de importação do Office 365 para importar os dados PST para as caixas de correio na sua organização. 

- **Envio de Unidade** ![Disco rígido](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - Copia os arquivos PST em uma unidade de disco rígido e, em seguida, envia essa unidade fisicamente para a Microsoft. Quando a Microsoft recebe o disco rígido, a equipe do data center carrega os dados para um local temporário de Armazenamento do Azure na nuvem da Microsoft. Em seguida, use o serviço de importação do Office 365 para importar os dados para as caixas de correio na sua organização.

## <a name="step-by-step-instructions"></a>Instruções passo a passo
  
Confira um dos tópicos a seguir para obter instruções detalhadas, passo a passo, para importar arquivos PST da sua organização para o Office 365. 

- [Usar o carregamento de rede para importar arquivos PST para o Office 365](use-network-upload-to-import-pst-files.md)

- [Usar o envio de unidade para importar arquivos PST](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>Como funciona a importação de arquivos PST

Esta é uma ilustração e uma descrição do processo de importação de PST completo. A ilustração mostra o fluxo de trabalho principal e realça as diferenças entre o carregamento de rede e os métodos de envio de unidade.
  
![Fluxo de trabalho de processo de importação de PST](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)
  
1. **Baixar as ferramentas de importação PST e a chave para o local privado de Armazenamento do Azure** - A primeira etapa é baixar a ferramenta e a chave de acesso usadas para carregar os arquivos PST ou copiá-los para um disco rígido. Você obtém isso na página **Importar** no Centro de Conformidade e Segurança. A chave fornece a você (ou a equipe de data center da Microsoft em caso de envio de unidades) as permissões necessárias para carregar arquivos PST em um local privado de Armazenamento do Azure. Essa chave de acesso é exclusiva à sua organização e ajuda a impedir o acesso não autorizado aos seus arquivos PST depois que eles são carregados na nuvem da Microsoft. Observe que importar arquivos PST para o Microsoft 365 não exige que sua organização tenha uma assinatura separada do Azure. 
    
2. **Carregue ou copie os arquivos PST** - A próxima etapa depende se você estiver usando o carregamento de rede ou o envio de unidade para importar arquivos PST. Em ambos os casos, você usará a ferramenta e a chave do armazenamento seguro obtida na etapa anterior.
    
    - **Carregamento de rede:** a ferramenta AzCopy.exe (baixada na etapa 1) é usada para carregar e armazenar os arquivos PST em um local de armazenamento do Azure na nuvem da Microsoft.  O local de Armazenamento do Azure em que você carrega os arquivos PST está localizado no mesmo datacenter da Microsoft que sua organização está.
    
      Para carregá-los, os arquivos PST que você deseja importar devem estar localizados em um compartilhamento de arquivos ou em um servidor de arquivos em sua organização.
    
    - **Envio de unidades:** a ferramenta WAImportExport.exe (baixada na etapa 1) é usada para copiar os arquivos PST para o disco rígido. Essa ferramenta criptografa o disco rígido com BitLocker e, em seguida, copia os PSTs para o disco rígido. Como o carregamento de rede, os arquivos PST que você deseja copiar para o disco rígido devem estar localizados em um compartilhamento de arquivos ou em um servidor de arquivos em sua organização.
    
3. **Criar um arquivo de mapeamento de importação de PST** - Depois de carregar os arquivos PST para o local de Armazenamento do Azure ou copiá-los para um disco rígido, a próxima etapa é criar um arquivo de valores separados por vírgula (CSV) que especifica para quais caixas de correio de usuário os arquivos PST serão importados (um arquivo PST pode ser importado para a caixa de correio principal do usuário ou para a caixa de correio de arquivo morto). O serviço de importação do Office 365 usará as informações para importar os arquivos PST. 
    
4. **Criar um trabalho de importação PST** - A próxima etapa é criar um trabalho de importação PST na página **Importar arquivos PST** no Centro de Conformidade e Segurança e enviar o arquivo de mapeamento de importação PST criado na etapa anterior. Para carregamento de rede (como os arquivos PST foram carregados para o Azure), o Microsoft 365 analisa os dados nos arquivos PST e oferece a você a oportunidade de definir filtros que controlam quais dados serão importados para as caixas de correio especificadas no arquivos de mapeamento de importação de PST. 
    
    Para o envio de unidades, algumas coisas adicionais acontecem neste momento do processo.
    
    - Você envia fisicamente o disco rígido para um data center da Microsoft (o endereço de envio para o data center da Microsoft é exibido quando o trabalho de importação é criado).
    
    - Quando a Microsoft recebe o disco rígido, a equipe do data center carregará os arquivos PST no disco rígido para o local de Armazenamento do Azure da sua organização. Como explicado anteriormente, os arquivos PST são carregados em um local de Armazenamento do Azure que está localizado no mesmo datacenter regional da Microsoft em que sua organização está.
    
      > [!NOTE]
      > Os arquivos PST do disco rígido são carregados para o Azure dentro de sete a 10 dias úteis, depois que a Microsoft recebe o disco rígido.

      Assim como o processo de carregamento de rede, o Microsoft 365 analisa os dados dos arquivos PST e oferece a oportunidade de definir filtros que controlam quais dados serão importados para as caixas de correio especificadas no arquivo de mapeamento de importação de PST.
    
    - A Microsoft envia o disco rígido de volta para você.
    
5. **Filtrar os dados PST que serão importados para as caixas de correio** - Depois que o trabalho de importação é criado (e depois que os arquivos PST de um serviço de envio de unidade são carregados no local de Armazenamento do Azure), o Microsoft 365 analisa os dados nos arquivos PST (de forma segura) identificando a idade dos itens e os diferentes tipos de mensagens incluídas nos arquivos PST. Quando esta análise for concluída e os dados estiverem prontos para importação, você terá a opção de importar todos os dados contidos nos arquivos PST ou cortar os dados que serão importados configurando filtros para controlar quais dados serão importados. 
    
6. **Inicie o trabalho de importação de PST:** - Depois que o trabalho de importação é iniciado, o Microsoft 365 usa as informações do arquivo de mapeamento de importação PST para importar os arquivos PSTs do local de armazenamento do Azure para as caixas de correio de usuário. Informações de status sobre o trabalho de importação (incluindo informações sobre cada arquivo PST que está sendo importado) são exibidas na página **Importar arquivos PST** no Centro de Conformidade e Segurança. Quando o trabalho de importação for concluído, o status do trabalho será definido como **Concluído**. 
  
## <a name="why-import-email-data-to-microsoft-365"></a>Por que importar dados de email para o Microsoft 365?

- É uma boa maneira de importar os dados de mensagens de arquivamento da sua organização para o Microsoft 365.
    
- Você pode usar o recurso de [Importação Inteligente](filter-data-when-importing-pst-files.md) para filtrar os itens nos arquivos PST que são importados para as caixas de correio de destino. Isso permite que você corte os dados que são importados configurando filtros que controlam quais dados serão importados. 
    
- Importar dados de email para o Microsoft 365 ajuda a atender às necessidades de conformidade da organização, permitindo:
    
  - Habilitar as [caixas de correio de arquivo morto](enable-archive-mailboxes.md) e [arquivamento ilimitado](unlimited-archiving.md) para conceder aos usuários mais espaço de armazenamento de caixa de correio. 
    
  - Colocar as caixas de correio em [Retenção de Litígio](https://go.microsoft.com/fwlink/?linkid=841243) para reter conteúdo. 
    
  - Usar a [ferramenta de Pesquisa de Conteúdo](content-search.md) para pesquisar conteúdo de caixa de correio. 
    
  - Usar os [casos de Descoberta Eletrônica](ediscovery-cases.md) para gerenciar as investigações jurídicas de sua organização. 
    
  - Usar as [políticas de retenção](retention-policies.md) no Centro de Conformidade e Segurança para controlar por quanto tempo o conteúdo da caixa de correio fica retido e, em seguida, exclua o conteúdo depois que o período de retenção expirar. 

  - Usar [Políticas de conformidade de comunicação](communication-compliance.md) para examinar as mensagens e se certificar que elas estão em conformidade com os padrões de mensagem e adicionar um tipo de classificação.
    
- Importar dados para o Microsoft 365 ajuda na proteção contra perda de dados. Os dados de email importados para o Microsoft 365 herdam recurso de alta disponibilidade do Exchange Online.
    
- Os dados de email ficam disponíveis para os usuários em todos os dispositivos, já que são armazenados na nuvem.
    
## <a name="importing-sharepoint-data-to-microsoft-365"></a>Importar dados do SharePoint para o Microsoft 365

É possível também importar arquivos e documentos para os sites do SharePoint e contas do OneDrive na sua organização. Para saber mais, confira os seguintes artigos:

- [Migrar para o SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)

- [Apresentando a Ferramenta de Migração do SharePoint](https://docs.microsoft.com/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [Migrar para o SharePoint Online usando o Windows PowerShell](https://docs.microsoft.com/sharepointmigration/overview-spmt-ps-cmdlets)

- [Migrar o conteúdo do compartilhamento de arquivo para o SharePoint Online usando o Azure Data Box](https://docs.microsoft.com/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)


## <a name="frequently-asked-questions-about-importing-pst-files"></a>Perguntas frequentes sobre a importação de arquivos PST
  
Para ver perguntas frequentes sobre o uso do serviço de importação do Office 365 para importar arquivos PST em massa às caixas de correio do Microsoft 365. 
  
- [Usar o carregamento de rede para importar arquivos PST](#using-network-upload-to-import-pst-files)
  
- [Usar a entrega de unidade para importar arquivos PST](#using-drive-shipping-to-import-pst-files)
  
### <a name="using-network-upload-to-import-pst-files"></a>Usar o carregamento de rede para importar arquivos PST

 **Quais permissões são necessárias para criar trabalhos de importação no serviço de importação do Office 365?**
  
Você deverá ter a função Exportação Importação da Caixa de Correio no Exchange Online para importar arquivos PST para as caixas de correio do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importação e Exportação de Caixa de Correio no grupo de função Gerenciamento da Organização. Ou pode criar um novo grupo de funções, atribuir a função Exportação Importação da Caixa de Correio e adicionar a si mesmo ou outros usuários como membros. Para mais informações, confira as seções “Adicionar uma função a um grupo de funções” ou “Criar um grupo de funções” em [Gerenciar grupos de funções no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Além disso, para criar trabalhos de importação no Centro de Conformidade e Segurança, uma das alternativas a seguir deve ser verdadeira:
  
- Você precisa ter a função Destinatários de email no Exchange Online. Por padrão, essa função é atribuída aos grupos de funções Gerenciamento da Organização e Gerenciamento de Destinatários.

    Ou
    
- É necessário que você seja um administrador global na sua organização.

> [!TIP]
> Considere a criação de um novo grupo de função no Exchange Online destinado especificamente a importar os arquivos PST para o Office 365. Para o nível mínimo de privilégios necessários para importar os arquivos PST, atribua as funções de Exportação Importação de Caixa de Correio e Destinatários de email ao novo grupo de função e, em seguida, adicione membros. 
  
 **Onde o carregamento de rede está disponível?**
  
O carregamento de rede está disponível nessas regiões: Estados Unidos, Canadá, Brasil, Reino Unido, Europa, Índia, Leste Asiático, Sudeste Asiático, Japão, República da Coreia e Austrália. O carregamento de rede estará disponível em mais regiões em breve.

> [!NOTE]
> No momento, não é possível carregar os arquivos PST na Alemanha e na Suíça. Estas Perguntas Mais Frequentes serão atualizadas quando o carregamento de rede estiver disponível nestes países.
  
 **Qual é o custo de importação dos arquivos PST usando o carregamento de rede?**
  
Using network upload to import PST files is free.
  
Isso também significa que depois que os arquivos PST forem excluídos da área de Armazenamento do Azure, eles não serão mais exibidos na lista de arquivos de um trabalho de importação concluído no centro de administração do Microsoft 365. Embora um trabalho de importação ainda possa estar listado na página **Importar dados para o Office 365**, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação anteriores.
  
 **Qual versão do formato de arquivo PST é compatível com a importação para o Office 365?**
  
Há duas versões do formato de arquivo PST: ANSI e Unicode. Recomendamos importar arquivos que usem o formato de arquivo PST Unicode. No entanto, os arquivos que utilizam o formato de arquivo PST ANSI, como aqueles para linguagens que utilizam um conjunto de caracteres de bytes duplos (DBCS), também podem ser importados para o Office 365. Para obter mais informações sobre como importar arquivos PST ANSI, confira a Etapa 4 em [Usar o carregamento de rede para importar arquivos PST para o Office 365](https://go.microsoft.com/fwlink/p/?LinkId=823074).
  
Além disso, os arquivos PST do Outlook 2007 e versões posteriores podem ser importados para o Office 365.
  
 **Depois de carregar meus arquivos PST para a área de Armazenamento do Azure, quanto tempo eles serão mantidos no Azure até serem excluídos?**
  
Quando você usar o método de carregamento de rede para importar arquivos PST, carregue-os para um contêiner de blobs chamado **ingestiondata**. Se não houver trabalhos de importação em andamento na página **Importar arquivos PST** no Centro de Conformidade e Segurança, todos os arquivos PST no contêiner **ingestiondata** no Azure serão excluídos 30 dias após a criação do trabalho de importação mais recente no Centro de Conformidade e Segurança. Isso também significa que você precisar criar um novo trabalho de importação no Centro de Conformidade e Segurança (descrito na etapa 5 nas instruções de carregamento de rede) dentro de 30 dias do carregamento de arquivos PST para o Azure.
  
Isso também significa que depois que os arquivos PST forem excluídos da área de Armazenamento do Azure, eles não serão mais exibidos na lista de arquivos de um trabalho de importação concluído no Centro de Conformidade e Segurança. Embora um trabalho de importação ainda possa estar listado na página **Importar arquivos PST** no Centro de Conformidade e Segurança, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação anteriores.
  
 **Quanto tempo é necessário para importar um arquivo PST para uma caixa de correio?**
  
Isso depende da capacidade da sua rede, mas normalmente cada terabyte (TB) leva várias horas para ser carregado para a área de Armazenamento do Azure da sua organização. Após copiar os arquivos PST para a área de Armazenamento do Azure, um arquivo PST é importado para uma caixa de correio do Microsoft 365 a uma taxa de pelo menos 24 GB por dia. Se essa taxa não atender às suas necessidades, considere outros métodos para obter dados de email para o Office 365. Para saber mais, confira o artigo [Formas de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Quando diferentes arquivos PST são importados para diferentes caixas de correio de destino, o processo de importação ocorre em paralelo; em outras palavras, cada par PST/caixa de correio é importado simultaneamente. Da mesma maneira, quando vários arquivos PST são importados para a mesma caixa de correio, eles são importados simultaneamente.
  
 **Como o processo de importação de PST controla os itens de email duplicados?**

O processo de importação de PST verifica itens duplicados e não copia os itens do arquivo PST na caixa de correio ou arquivo se um item correspondente existe na caixa de correio de destino ou arquivo de destino. Se você importar novamente o mesmo arquivo PST e especificar uma pasta de destino diferente (usando a propriedade TargetRootFolder no arquivo de mapeamento de importação de PST) do que a que você especificou em um trabalho de importação anterior, todos os itens do arquivo PST serão importados novamente.
 
 **Há um limite de tamanho de mensagem ao importar arquivos PST?**
  
Sim. Quando um arquivo PST inclui um item de caixa de correio com mais de 150 MB, o item é ignorado durante o processo de importação.
  
 **As propriedades da mensagem, como quando a mensagem foi enviada ou recebida, a lista de destinatários e outras propriedades, são mantidas quando os arquivos PST são importados para uma caixa de correio do Microsoft 365?**
  
Sim. Os metadados da mensagem original não são alterados durante o processo de importação.
  
 **Há um limite para o número de níveis em uma hierarquia de pastas de um arquivo PST que quero importar para uma caixa de correio?**
  
Sim. Não é possível importar um arquivo PST com 300 ou mais níveis de pastas aninhadas.
  
 **Posso usar o carregamento de rede para importar arquivos PST para uma caixa de correio inativa no Office 365?**
  
Sim, esse recurso já está disponível.
  
 **Posso usar o carregamento de rede para importar arquivos PST para uma caixa de correio de arquivo morto online em uma implantação híbrida do Exchange?**
  
Sim, esse recurso já está disponível. 
  
 **Posso usar o carregamento de rede para importar arquivos PST para pastas públicas no Exchange Online?**
  
Não. Não é possível importar arquivos PST para pastas públicas.
  
### <a name="using-drive-shipping-to-import-pst-files"></a>Usar a entrega de unidade para importar arquivos PST

 **Quais permissões são necessárias para criar trabalhos de importação no serviço de importação do Office 365?**
  
Você deve ter a função Importação Exportação da Caixa de Correio para importar arquivos PST para as caixas de correio do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importação e Exportação de Caixa de Correio no grupo de função Gerenciamento da Organização. Ou pode criar um novo grupo de funções, atribuir a função Exportação Importação da Caixa de Correio e adicionar a si mesmo ou outros usuários como membros. Para mais informações, confira as seções “Adicionar uma função a um grupo de funções” ou “Criar um grupo de funções” em [Gerenciar grupos de funções no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Além disso, para criar trabalhos de importação no Centro de Conformidade e Segurança, uma das alternativas a seguir deve ser verdadeira:
  
- Você precisa ter a função Destinatários de email no Exchange Online. Por padrão, essa função é atribuída aos grupos de funções Gerenciamento da Organização e Gerenciamento de Destinatários.
    
    Ou
    
- É necessário que você seja um administrador global na sua organização.
    
> [!TIP]
> Considere a criação de um novo grupo de função no Exchange Online destinado especificamente a importar os arquivos PST para o Office 365. Para o nível mínimo de privilégios necessários para importar os arquivos PST, atribua as funções de Exportação Importação de Caixa de Correio e Destinatários de email ao novo grupo de função e, em seguida, adicione membros. 
  
 **Onde o envio de unidade está disponível?**
  
No momento, o envio de unidades está disponível nas seguintes regiões: Austrália, Brasil, Canadá, Estados Unidos, Europa, Índia, Japão, Leste Asiático, Sudeste Asiático, Reino Unido e República da Coreia. O envio de unidades estará disponível para mais regiões em breve.

> [!NOTE]
> No momento, não é possível carregar os arquivos PST na Alemanha e na Suíça. Estas Perguntas Mais Frequentes serão atualizadas quando o carregamento de rede estiver disponível nestes países.
  
 **Quais contratos de licenciamento comercial dão suporte ao envio de unidade?**
  
O envio de unidade para importar arquivos PST para o Microsoft 365 está disponível por meio de um Contrato Enterprise (EA) da Microsoft. O envio de unidade não está disponível por meio de um Contrato de Produtos e Serviços da Microsoft (MPSA).
  
 **Qual é o custo para usar o envio de unidade para importar arquivos PST para o Microsoft 365?**
  
O custo para usar o envio de unidade para importar arquivos PST para caixas de correio do Microsoft 365 é de US$ 2 por GB de dados. Por exemplo, se você enviar um disco rígido contendo 1.000 GB (1 TB) de arquivos PST, o custo será de US$ 2.000. Você pode trabalhar com um parceiro para pagar a taxa de importação. Para obter mais informações sobre como encontrar um parceiro, confira [Encontrar seu parceiro ou revendedor do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=785197).
  
 **Que tipos de discos rígidos têm suporte para o envio de unidade?**
  
Somente as unidades de estado sólido (SSDs) de 2,5 polegadas ou discos rígidos internos SATA II/III de 2,5 ou 3,5 polegadas são compatíveis para o uso com o serviço de Importação do Office 365. Use discos rígidos de até 10 TB. Para trabalhos de importação, somente o primeiro volume de dados do disco rígido será processado. O volume de dados deve ser formatado com NTFS. Ao copiar dados para um disco rígido, é possível anexá-los diretamente usando um SSD de 2,5 polegadas ou um conector SATA II/III de 2,5 ou 3,5 polegadas, ou pode ainda anexá-lo externamente usando um SSD externo de 2,5 polegadas ou um adaptador USB SATA II/III de 2,5 ou 3,5 polegadas.
  
> [!IMPORTANT]
> As unidades de disco rígido com um adaptador USB interno não são compatíveis com o serviço de importação do Office 365. Além disso, o disco dentro da caixa do disco rígido externo não pode ser utilizado. Não remova discos rígidos externos. 
  
 **Quantas unidades de disco rígido posso enviar para um único trabalho de importação?**
  
Você pode enviar no máximo 10 discos rígidos para um único trabalho de importação.
  
 **Depois de enviar meu disco rígido, quanto tempo leva para chegar ao datacenter da Microsoft?**
  
Isso depende de alguns pontos, como da sua proximidade com o data center da Microsoft e com o tipo de opção de envio utilizada para enviar o seu disco rígido (como, entrega no próximo dia, entrega em dois dias ou entrega em tempo normal). Com a maioria das transportadoras, é possível usar o número de rastreamento para acompanhar o status da entrega.
  
 **Depois que meu disco rígido chega ao datacenter da Microsoft, quanto tempo leva para carregar meus arquivos PST no Azure?**
  
Depois que seu disco rígido for recebido no data center da Microsoft, serão necessários de 7 a 10 dias úteis para carregar os arquivos PST na local de Armazenamento do Azure da sua organização. Os arquivos PST serão carregados para o contêiner de blob do Azure chamado `ingestiondata`. 
  
 **Quanto tempo é necessário para importar um arquivo PST para uma caixa de correio?**
  
Depois que os arquivos PST são carregados na área de Armazenamento do Azure, o Microsoft 365 analisa os dados nos arquivos PST (de maneira segura) para identificar a idade dos itens e os diferentes tipos de mensagens incluídos nos arquivos PST. Quando esta análise for concluída, você terá a opção de importar todos os dados nos arquivos PST ou configurar filtros para controlar quais dados serão importados. Depois de iniciar o trabalho de importação, um arquivo PST será importado para uma caixa de correio do Microsoft 365 a uma taxa de pelo menos 24 GB por dia. Se essa taxa não atender às suas necessidades, considere outros métodos para obter dados de email para o Microsoft 365. Para saber mais, confira o artigo [Formas de migrar várias contas de email para o Microsoft 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Quando diferentes arquivos PST são importados para diferentes caixas de correio de destino, o processo de importação ocorre em paralelo; em outras palavras, cada par PST/caixa de correio é importado simultaneamente. Da mesma maneira, quando vários arquivos PST são importados para a mesma caixa de correio, eles são importados simultaneamente.
  
 **Depois que a Microsoft carregar meus arquivos PST para o Azure, por quanto tempo eles serão mantidos no Azure até serem excluídos?**
  
Todos os arquivos PST, no local de Armazenamento do Azure da sua organização (no contêiner de blob chamado `ingestiondata`), serão excluídos 30 dias depois que o trabalho de importação mais recente tiver sido criado na página **Importar arquivos PST** no Centro de Conformidade e Segurança. 
  
Isso também significa que depois que os arquivos PST forem excluídos da área de Armazenamento do Azure, eles não serão mais exibidos na lista de arquivos de um trabalho de importação concluído no Centro de Conformidade e Segurança. Embora um trabalho de importação ainda possa estar listado na página **Importar arquivos PST** no Centro de Conformidade e Segurança, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação anteriores. 
  
 **Qual versão do formato de arquivo PST é compatível com a importação para o Microsoft 365?**
  
Há duas versões do formato de arquivo PST: ANSI e Unicode. Recomendamos importar arquivos que usem o formato de arquivo PST Unicode. No entanto, os arquivos que utilizam o formato de arquivo PST ANSI, como aqueles para linguagens que utilizam um conjunto de caracteres de bytes duplos (DBCS), também podem ser importados para o Microsoft 365. Para obter mais informações sobre como importar arquivos PST ANSI, confira a Etapa 3 em [Usar o envio de unidade para importar arquivos PST para o Microsoft 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Além disso, os arquivos PST do Outlook 2007 e versões posteriores podem ser importados para o Microsoft 365.
  
 **Há um limite de tamanho de mensagem ao importar arquivos PST?**
  
Sim. Quando um arquivo PST inclui um item de caixa de correio com mais de 150 MB, o item é ignorado durante o processo de importação.
  
  **Como o processo de importação de PST controla os itens de email duplicados?**

O processo de importação de PST verifica itens duplicados e não copia os itens do arquivo PST na caixa de correio ou arquivo se um item correspondente existe na caixa de correio de destino ou arquivo de destino. Se você importar novamente o mesmo arquivo PST e especificar uma pasta de destino diferente (usando a propriedade TargetRootFolder no arquivo de mapeamento de importação de PST) do que a que você especificou em um trabalho de importação anterior, todos os itens do arquivo PST serão importados novamente.
 
 **As propriedades da mensagem, como quando a mensagem foi enviada ou recebida, a lista de destinatários e outras propriedades, são mantidas quando os arquivos PST são importados para uma caixa de correio do Microsoft 365?**
  
Sim. Os metadados da mensagem original não são alterados durante o processo de importação
  
 **Há um limite para o número de níveis em uma hierarquia de pastas de um arquivo PST que quero importar para uma caixa de correio?**
  
Sim. Não é possível importar um arquivo PST com 300 ou mais níveis de pastas aninhadas.
  
 **Posso usar o envio de unidade para importar arquivos PST para uma caixa de correio inativa no Microsoft 365?**
  
Sim, esse recurso já está disponível.
  
 **Posso usar o envio de unidade para importar arquivos PST para uma caixa de correio de arquivo morto online em uma implantação híbrida do Exchange?**
  
Sim, esse recurso já está disponível. 
  
 **Posso usar o envio de unidade para importar arquivos PST para pastas públicas no Exchange Online?**
  
Não. Não é possível importar arquivos PST para pastas públicas.
  
 **A Microsoft pode apagar meu disco rígido antes de enviá-lo de volta para mim?**
  
Não, a Microsoft não pode apagar discos rígidos antes de enviá-los de volta aos clientes. Os discos rígidos são devolvidos no mesmo estado em que estavam quando foram recebidos pela Microsoft.
  
 **A Microsoft pode destruir meu disco rígido em vez de enviá-lo de volta para mim?**
  
Não, a Microsoft não pode destruir seu disco rígido. Os discos rígidos são devolvidos no mesmo estado em que estavam quando foram recebidos pela Microsoft.
  
 **Quais serviços de entrega têm suporte para a remessa de devolução?**
  
Se você estiver nos Estados Unidos ou na Europa, a Microsoft utilizará a FedEx para a devolução do seu disco rígido. Para todas as demais regiões, a Microsoft utilizará a DHL.
  
 **Quais são os custos da remessa de devolução?**
  
Os custos da remessa de devolução variam, dependendo da sua proximidade em relação ao data center da Microsoft para o qual você enviou o seu disco rígido. A Microsoft cobrará o valor cobrado pela FedEx ou DHL para a devolução do seu disco rígido. O custo para a remessa de devolução é de sua responsabilidade.
  
 ** Posso usar um serviço de entrega personalizado, como a Remessa Personalizada da FedEx, para enviar meu disco rígido à Microsoft? **
  
Sim.
  
 **Se eu tiver que enviar meu disco rígido para outro país, há algo que precise ser feito?**
  
O disco rígido que você enviará para a Microsoft terá talvez que cruzar fronteiras internacionais. Se esse for o caso, você é responsável por garantir que o disco rígido e os dados contidos nele sejam importados e/ou exportados de acordo com a legislação aplicável. Antes de enviar um disco rígido, verifique com seu consultores se a unidade e os dados podem ser legalmente enviados para o centro de dados especificado da Microsoft. Isso ajudará a garantir que ele chegue à Microsoft em tempo hábil.
