---
title: Alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de descoberta eletrônica
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
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: Você pode alterar o tamanho padrão dos arquivos PST que são baixados para o seu computador quando exporta os resultados da pesquisa de descoberta eletrônica.
ms.openlocfilehash: f5fde9bbb37f6e22c49049c892a1b69b07d15bef
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636319"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>Alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de descoberta eletrônica

Ao usar a ferramenta de exportação de descoberta eletrônica para exportar os resultados de email de uma pesquisa de descoberta eletrônica das diferentes ferramentas de descoberta eletrônica da Microsoft, o tamanho padrão de um arquivo PST que pode ser exportado é de 10 GB. Se você quiser alterar esse tamanho padrão, poderá editar o registro do Windows no computador que você usa para exportar os resultados da pesquisa. Uma razão para fazer isso é que um arquivo PST pode se ajustar em mídia removível, como DVD, CD ou unidade USB. 
  
> [!NOTE]
> A ferramenta de exportação de descoberta eletrônica é usada para exportar os resultados da pesquisa ao usar a ferramenta de pesquisa de conteúdo no centro de conformidade e segurança &, descoberta eletrônica in-loco no Exchange Online e o centro de descoberta eletrônica no SharePoint Online.
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Criar uma configuração de registro para alterar o tamanho dos arquivos PST ao exportar os resultados da pesquisa de descoberta eletrônica

Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de descoberta eletrônica.
  
1. Feche a ferramenta de exportação de descoberta eletrônica, se ela estiver aberta. 
    
2. Salve o seguinte texto em um arquivo de registro de janela usando um sufixo de nome de arquivo. reg; por exemplo, PstExportSize. reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    No exemplo acima, o `PstSizeLimitInBytes` valor é definido como 1.073.741.824 bytes ou aproximadamente 1 GB. Aqui estão alguns outros valores de exemplo para `PstSizeLimitInBytes` a configuração. 
    
    |**Tamanho em GB (aprox.)**|**Tamanho em bytes**|
    |:-----|:-----|
    |0,7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. Altere o `PstSizeLimitInBytes` valor para o tamanho máximo desejado de um arquivo PST ao exportar os resultados da pesquisa e salve o arquivo. 
    
4. No Windows Explorer, clique ou clique duas vezes no arquivo. reg que você criou nas etapas anteriores.
    
5. Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração. 
    
6. Quando for solicitado a continuar, clique em **Sim**.
    
    O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.
    
7. Você pode repetir as etapas 3-6 para alterar o valor da `PstSizeLimitInBytes` configuração do registro. 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>Perguntas frequentes sobre como alterar o tamanho padrão de arquivos PST quando você exporta os resultados da pesquisa de descoberta eletrônica

 **Por que o tamanho padrão é de 10 GB?**
  
O tamanho padrão de 10 GB era baseado nos comentários dos clientes; 10 GB é um bom equilíbrio entre a quantidade ideal de conteúdo em um único PST e com uma chance mínima de danos no arquivo.
  
 **Devo aumentar ou diminuir o tamanho padrão dos arquivos PST?**
  
Os clientes tendem a reduzir o limite de tamanho para que os resultados da pesquisa caibam em mídia removível que eles podem enviar fisicamente para outros locais em sua organização. Não é recomendável aumentar o tamanho padrão porque os arquivos PST com mais de 10 GB podem ter problemas de corrupção.
  
 **Em qual computador tenho que fazer isso?**
  
Você precisa alterar a configuração do registro em qualquer computador local em que executa a ferramenta de exportação de descoberta eletrônica.
  
 **Após alterar essa configuração, preciso reinicializar o computador?**
  
Não, não é necessário reinicializar o computador. No entanto, se a ferramenta de exportação de descoberta eletrônica estiver em execução, você terá que fechá-la e reiniciá-la depois de alterar essa configuração.
  
 **Uma chave de registro existente é editada ou faz uma nova chave ser criada?**
  
Uma nova chave de registro é criada na primeira vez que você executa o arquivo. reg que você criou neste procedimento. Em seguida, a configuração será editada sempre que você alterar e executar novamente o arquivo. reg Edit.
