---
title: Alterar o tamanho dos arquivos PST ao exportar resultados da pesquisa de Descobertas Digitais
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Você pode alterar o tamanho padrão dos arquivos PST baixados para o computador quando você exporta os resultados da pesquisa de Descobertas Digitais.
ms.openlocfilehash: eb5fcce037ff5e3444b42c996b4a32d818edd29d
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43942914"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Alterar o tamanho dos arquivos PST ao exportar resultados da pesquisa de Descobertas Digitais

Quando você usa a ferramenta Exportação de Descoberta Eletrônico para exportar os resultados de email de uma pesquisa de Descoberta Eletrônico das diferentes ferramentas de Descoberta Eletrônico da Microsoft, o tamanho padrão de um arquivo PST que pode ser exportado é de 10 GB. Se você quiser alterar esse tamanho padrão, poderá editar o registro Windows no computador que você usa para exportar os resultados da pesquisa. Um motivo para fazer isso é para que um arquivo PST possa caber em mídia removível, como um DVD, um disco compacto ou uma unidade USB. 
  
> [!NOTE]
> A ferramenta Exportação de Descoberta Virtual é usada para exportar os resultados da pesquisa ao usar a ferramenta Pesquisa de Conteúdo no Centro de Conformidade e Segurança do &, In-Place Descoberta Virtual no Exchange Online e o Centro de Descoberta Virtual no SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Criar uma configuração do Registro para alterar o tamanho dos arquivos PST quando você exportar resultados da pesquisa de Descoberta e

Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de Descoberta e.
  
1. Feche a ferramenta Exportação de Descoberta Digital se estiver aberta. 
    
2. Salve o texto a seguir em um arquivo de Registro de Janela usando um sufixo de nome de arquivo de .reg; por exemplo, PstExportSize.reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    No exemplo acima, o valor é definido como  `PstSizeLimitInBytes` 1.073.741.824 bytes ou aproximadamente 1 GB. Aqui estão alguns outros valores de exemplo para a  `PstSizeLimitInBytes` configuração. 
    
    |**Tamanho em GB (aprox.)**|**Tamanho em bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Altere o valor para o tamanho máximo desejado de um arquivo PST quando você exportar os resultados da pesquisa e `PstSizeLimitInBytes` salve o arquivo. 
    
4. No Windows Explorer, clique ou clique duas vezes no arquivo .reg que você criou nas etapas anteriores.
    
5. Na janela Controle de Acesso para Usuário, clique em **Sim** para permitir que o Editor do Registro faça a alteração. 
    
6. Quando solicitado a continuar, clique em **Sim**.
    
    O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.
    
7. Você pode repetir as etapas 3 a 6 para alterar o valor da  `PstSizeLimitInBytes` configuração do Registro. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Perguntas frequentes sobre como alterar o tamanho padrão de arquivos PST quando você exporta resultados de pesquisa de Descoberta e

 **Por que o tamanho padrão é 10 GB?**
  
O tamanho padrão de 10 GB foi baseado nos comentários do cliente; 10 GB é um bom equilíbrio entre a quantidade ideal de conteúdo em um único PST e com uma chance mínima de corrupção de arquivo.
  
 **Devo aumentar ou diminuir o tamanho padrão de arquivos PST?**
  
Os clientes tendem a diminuir o limite de tamanho para que os resultados da pesquisa se encaixem em mídia removível que eles possam enviar fisicamente para outros locais em sua organização. Não recomendamos que você aumente o tamanho padrão porque arquivos PST maiores do que 10 GB podem ter problemas de corrupção.
  
 **Em qual computador devo fazer isso?**
  
Você precisa alterar a configuração do Registro em qualquer computador local em que você execute a ferramenta Exportar Descoberta e.
  
 **Depois de alterar essa configuração, preciso reiniciar o computador?**
  
Não, você não precisa reiniciar o computador. Mas, se a ferramenta Exportação de Descoberta Digital estiver em execução, você terá que fechar e reinicie-a depois de alterar essa configuração.
  
 **Uma chave existente do Registro é editada ou uma nova chave é criada?**
  
Uma nova chave do Registro é criada na primeira vez que você executar o arquivo .reg criado neste procedimento. Em seguida, a configuração é editada sempre que você alterar e reprisar o arquivo de edição .reg.
