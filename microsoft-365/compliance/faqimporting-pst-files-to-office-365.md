---
title: Perguntas Frequentes sobre a importação de arquivos PST
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 2fe71b05-f5a2-4182-ade7-4dc5cabdfd51
description: 'Perguntas frequentes para administradores sobre como usar o serviço de importação do Office 365 para importar arquivos PST da sua organização para caixas de correio do Microsoft 365. '
ms.openlocfilehash: 0d3245c962c2d22f0d500aafe22703bd3e57d504
ms.sourcegitcommit: a418195dc11e6251ae37e788c102bbaa7087e44e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44579196"
---
# <a name="faq-about-importing-pst-files"></a>Perguntas Frequentes sobre a importação de arquivos PST

**Este artigo é para administradores. Deseja importar arquivos PST para sua própria caixa de correio? Confira [importar email, contatos e calendário de um arquivo. pst do Outlook](https://go.microsoft.com/fwlink/p/?LinkID=785075)**|
   
Aqui estão algumas perguntas frequentes sobre como usar o serviço de importação do Office 365 para importar arquivos PST em massa para caixas de correio do Microsoft 365. Para obter mais informações sobre como importar arquivos PST, consulte [visão geral da importação de arquivos pst para o Office 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365).
  
## <a name="using-network-upload-to-import-pst-files"></a>Usar o carregamento de rede para importar arquivos PST

Para obter instruções passo a passo, consulte [usar o carregamento de rede para importar arquivos pst para o Office 365](use-network-upload-to-import-pst-files.md).
  
 **Quais permissões são necessárias para criar trabalhos de importação no serviço de importação do Office 365?**
  
Você deverá ter a função Exportação Importação da Caixa de Correio no Exchange Online para importar arquivos PST para as caixas de correio do Microsoft 365. Por padrão, essa função não é atribuída a nenhum grupo de funções no Exchange Online. Você pode adicionar a função Importação e Exportação de Caixa de Correio no grupo de função Gerenciamento da Organização. Ou pode criar um novo grupo de funções, atribuir a função Exportação Importação da Caixa de Correio e adicionar a si mesmo ou outros usuários como membros. Para mais informações, confira as seções “Adicionar uma função a um grupo de funções” ou “Criar um grupo de funções” em [Gerenciar grupos de funções no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=730688).
  
Além disso, para criar trabalhos de importação no Centro de Conformidade e Segurança, uma das alternativas a seguir deve ser verdadeira:
  
- Você precisa ter a função Destinatários de email no Exchange Online. Por padrão, essa função é atribuída aos grupos de funções Gerenciamento da Organização e Gerenciamento de Destinatários.
    
    Ou
    
- É necessário que você seja um administrador global na sua organização.
    
> [!TIP]
> Considere a criação de um novo grupo de função no Exchange Online destinado especificamente a importar os arquivos PST para o Office 365. Para o nível mínimo de privilégios necessários para importar os arquivos PST, atribua as funções de Exportação Importação de Caixa de Correio e Destinatários de email ao novo grupo de função e, em seguida, adicione membros. 
  
 **Onde o carregamento de rede está disponível?**
  
O carregamento de rede está disponível atualmente nestas áreas: Estados Unidos, Canadá, Brasil, Reino Unido, França, Europa, Índia, leste asiático, Sudeste Asiático, Japão, República da Coréia, Austrália e Emirados Árabes Unidos (Emirados). Network upload will be available in more regions soon.

> [!NOTE]
> No momento, não é possível carregar os arquivos PST na Alemanha e na Suíça. Estas Perguntas Mais Frequentes serão atualizadas quando o carregamento de rede estiver disponível nestes países.
  
 **Qual é o custo de importação dos arquivos PST usando o carregamento de rede?**
  
Using network upload to import PST files is free.
  
Isso também significa que depois que os arquivos PST forem excluídos da área de Armazenamento do Azure, eles não serão mais exibidos na lista de arquivos de um trabalho de importação concluído no centro de administração do Microsoft 365. Embora um trabalho de importação ainda possa estar listado na página **Importar dados para o Office 365**, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação anteriores. 
  
 **Qual versão do formato de arquivo PST é compatível com a importação para o Office 365?**
  
Há duas versões do formato de arquivo PST: ANSI e Unicode. Recomendamos importar arquivos que usem o formato de arquivo PST Unicode. No entanto, os arquivos que utilizam o formato de arquivo PST ANSI, como aqueles para linguagens que utilizam um conjunto de caracteres de bytes duplos (DBCS), também podem ser importados para o Office 365. Para obter mais informações sobre a importação de arquivos PST ANSI, consulte a etapa 4 em [usar o carregamento de rede para importar arquivos pst da sua organização para o Office 365](use-network-upload-to-import-pst-files.md#step-4-create-the-pst-import-mapping-file).
  
Além disso, os arquivos PST do Outlook 2007 e versões posteriores podem ser importados para o Office 365.
  
 **Depois de carregar meus arquivos PST para a área de Armazenamento do Azure, quanto tempo eles serão mantidos no Azure até serem excluídos?**
  
Quando você usar o método de carregamento de rede para importar arquivos PST, carregue-os para um contêiner de blobs chamado **ingestiondata**. Se não houver trabalhos de importação em andamento na página **Importar arquivos PST** no Centro de Conformidade e Segurança, todos os arquivos PST no contêiner **ingestiondata** no Azure serão excluídos 30 dias após a criação do trabalho de importação mais recente no Centro de Conformidade e Segurança. Isso também significa que você precisar criar um novo trabalho de importação no Centro de Conformidade e Segurança (descrito na etapa 5 nas instruções de carregamento de rede) dentro de 30 dias do carregamento de arquivos PST para o Azure. 
  
Isso também significa que depois que os arquivos PST forem excluídos da área de Armazenamento do Azure, eles não serão mais exibidos na lista de arquivos de um trabalho de importação concluído no Centro de Conformidade e Segurança. Embora um trabalho de importação ainda possa estar listado na página **Importar arquivos PST** no Centro de Conformidade e Segurança, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação anteriores. 
  
 **Quanto tempo é necessário para importar um arquivo PST para uma caixa de correio?**
  
Isso depende da capacidade da sua rede, mas normalmente cada terabyte (TB) leva várias horas para ser carregado para a área de Armazenamento do Azure da sua organização. Após copiar os arquivos PST para a área de Armazenamento do Azure, um arquivo PST é importado para uma caixa de correio do Microsoft 365 a uma taxa de pelo menos 24 GB por dia. Se essa taxa não atender às suas necessidades, considere a possibilidade de usar outros métodos para migrar dados de email para o Office 365. Para saber mais, confira o artigo [Formas de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
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
  
## <a name="using-drive-shipping-to-import-pst-files"></a>Usar a entrega de unidade para importar arquivos PST

Para obter instruções passo a passo, consulte [usar o envio de unidade para importar arquivos pst para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md).
  
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
  
Somente as unidades de estado sólido (SSDs) de 2,5 polegadas ou discos rígidos internos SATA II/III de 2,5 ou 3,5 polegadas são compatíveis para o uso com o serviço de importação do Office 365. Use discos rígidos de até 10 TB. Para trabalhos de importação, somente o primeiro volume de dados do disco rígido será processado. O volume de dados deve ser formatado com NTFS. Ao copiar dados para um disco rígido, é possível anexá-lo diretamente usando um SSD de 2,5 polegadas ou um conector SATA II/III de 2,5 ou 3,5 polegadas, ou pode ainda anexá-lo externamente usando um SSD externo de 2,5 polegadas ou um adaptador USB SATA II/III de 2,5 ou 3,5 polegadas.
  
> [!IMPORTANT]
> As unidades de disco rígido com um adaptador USB interno não são compatíveis com o serviço de importação do Office 365. Além disso, o disco dentro da caixa do disco rígido externo não pode ser utilizado. Não remova discos rígidos externos. 
  
 **Quantas unidades de disco rígido posso enviar para um único trabalho de importação?**
  
Você pode enviar no máximo 10 discos rígidos para um único trabalho de importação.
  
 **Após o envio do meu disco rígido, quanto tempo ele leva para chegar ao data center da Microsoft?**
  
Isso depende de alguns pontos, como da sua proximidade com o data center da Microsoft e com o tipo de opção de envio utilizada para enviar o seu disco rígido (como, entrega no próximo dia, entrega em dois dias ou entrega em tempo normal). Com a maioria das transportadoras, é possível usar o número de rastreamento para acompanhar o status da entrega.
  
 **Depois que meu disco rígido chegar ao data center da Microsoft, quanto tempo será necessário para carregar meus arquivos PST para o Azure?**
  
Depois que a unidade de disco rígido for recebida no Data Center da Microsoft, levará entre 7 e 10 dias úteis para carregar os arquivos PST para a área de armazenamento do Azure para sua organização. Os arquivos PST serão carregados para um contêiner de blob do Azure chamado **ingestiondata**. 
  
 **Quanto tempo é necessário para importar um arquivo PST para uma caixa de correio?**
  
Depois que os arquivos PST são carregados na área de Armazenamento do Azure, o Microsoft 365 analisa os dados nos arquivos PST (de maneira segura) para identificar a idade dos itens e os diferentes tipos de mensagens incluídos nos arquivos PST. Quando esta análise for concluída, você terá a opção de importar todos os dados nos arquivos PST ou configurar filtros para controlar quais dados serão importados. Depois de iniciar o trabalho de importação, um arquivo PST será importado para uma caixa de correio do Microsoft 365 a uma taxa de pelo menos 24 GB por dia. Se essa taxa não atender às suas necessidades, considere a possibilidade de usar outros métodos para importar dados de email para o Office 365. Para saber mais, confira o artigo [Formas de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
Quando diferentes arquivos PST são importados para diferentes caixas de correio de destino, o processo de importação ocorre em paralelo; em outras palavras, cada par PST/caixa de correio é importado simultaneamente. Da mesma maneira, quando vários arquivos PST são importados para a mesma caixa de correio, eles são importados simultaneamente.
  
 **Depois que a Microsoft carregar meus arquivos PST para o Azure, por quanto tempo eles serão mantidos no Azure até serem excluídos?**
  
Todos os arquivos PST no local de armazenamento do Azure para sua organização (no contêiner de blob chamado **ingestiondata**) são excluídos 30 dias após a criação do trabalho de importação mais recente na página **importar arquivos PST** no centro de conformidade do & de segurança. 
  
Isso também significa que depois que os arquivos PST forem excluídos da área de Armazenamento do Azure, eles não serão mais exibidos na lista de arquivos de um trabalho de importação concluído no Centro de Conformidade e Segurança. Embora um trabalho de importação ainda possa estar listado na página **Importar arquivos PST** no Centro de Conformidade e Segurança, a lista de arquivos PST pode estar vazia quando você exibir os detalhes de trabalhos de importação anteriores. 
  
 **Qual versão do formato de arquivo PST é compatível com a importação para o Microsoft 365?**
  
Há duas versões do formato de arquivo PST: ANSI e Unicode. Recomendamos importar arquivos que usem o formato de arquivo PST Unicode. No entanto, os arquivos que utilizam o formato de arquivo PST ANSI, como aqueles para linguagens que utilizam um conjunto de caracteres de bytes duplos (DBCS), também podem ser importados para o Microsoft 365. Para obter mais informações sobre a importação de arquivos PST ANSI, consulte a etapa 3 em [usar o envio de unidade para importar arquivos pst para o Office 365](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file).
  
Além disso, os arquivos PST do Outlook 2007 e versões posteriores podem ser importados para o Office 365.
  
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
