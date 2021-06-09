---
title: Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Edite o Windows registro em seu computador local para desabilitar relatórios ao exportar os resultados de uma Pesquisa de Conteúdo do Centro de Conformidade & Segurança.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817850"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo

Quando você usa a ferramenta Exportação de Descoberta Automática para exportar os resultados de uma Pesquisa de Conteúdo no Centro de Conformidade e Segurança, a ferramenta cria e exporta automaticamente dois relatórios que contêm informações adicionais sobre o conteúdo exportado. & Esses relatórios são o arquivo Results.csv e o arquivo [](#frequently-asked-questions-about-disabling-export-reports) Manifest.xml (consulte a seção Perguntas frequentes sobre como desabilitar relatórios de exportação neste tópico para descrições detalhadas desses relatórios). Como esses arquivos podem ser muito grandes, você pode acelerar o tempo de download e economizar espaço em disco impedindo que esses arquivos sejam exportados. Você pode fazer isso alterando a Windows registro no computador que você usa para exportar os resultados da pesquisa. Se quiser incluir os relatórios posteriormente, edite a configuração do Registro. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Criar configurações do Registro para desabilitar os relatórios de exportação

Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.
  
1. Feche a ferramenta Exportação de Descoberta Digital se estiver aberta.
    
2. Execute uma ou ambas as etapas a seguir, dependendo do relatório de exportação que você deseja desabilitar.
    
    - **Results.csv**
    
      Salve o texto a seguir em um arquivo Windows registro usando um sufixo de nome de arquivo de .reg; por exemplo, DisableResultsCsv.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      Salve o texto a seguir em um arquivo Windows registro usando um sufixo de nome de arquivo de .reg; por exemplo, DisableManifestXml.reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. No Windows Explorer, clique ou clique duas vezes no arquivo .reg que você criou nas etapas anteriores.
    
4. Na janela Controle de Acesso para Usuário, clique em **Sim** para permitir que o Editor do Registro faça a alteração. 
    
5. Quando solicitado a continuar, clique em **Sim**.
    
    O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Editar configurações do Registro para habilitar os relatórios de exportação

Se você desabilitou os relatórios Results.csv e Manifest.xml criando os arquivos .reg no procedimento anterior, você poderá editar esses arquivos para habilitar um relatório para que ele seja exportado com os resultados da pesquisa. Novamente, execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.
  
1. Feche a ferramenta Exportação de Descoberta Digital se estiver aberta.
    
2. Edite um ou ambos os arquivos de edição .reg criados no procedimento anterior.
    
    - **Results.csv**
    
        Abra o arquivo DisableResultsCsv.reg no Bloco de notas, altere o valor para `False` `True` e salve o arquivo. Por exemplo, depois de editar o arquivo, ele será assim:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        Abra o arquivo DisableManifestXml.reg no Bloco de notas, altere o valor `False` para e salve o `True` arquivo. Por exemplo, depois de editar o arquivo, ele será assim:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. No Windows Explorer, clique ou clique duas vezes em um arquivo .reg que você editou na etapa anterior.
    
4. Na janela Controle de Acesso para Usuário, clique em **Sim** para permitir que o Editor do Registro faça a alteração. 
    
5. Quando solicitado a continuar, clique em **Sim**.
    
    O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Perguntas frequentes sobre desabilitar relatórios de exportação

 **Quais são os Results.csv e Manifest.xml relatórios?**
  
Os arquivos Results.csv e Manifest.xml contêm informações adicionais sobre o conteúdo que foi exportado.
  
- **Results.csv** Um Excel que contém informações sobre cada item que é baixado como resultado da pesquisa. Para emails, o log do resultado contém informações sobre cada mensagem, incluindo: 
    
  - O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).
    
  - A data na qual a mensagem foi enviada ou recebida.
    
  - A linha de assunto da mensagem.
    
  - O remetente e os destinatários da mensagem.
    
  - Se a mensagem é uma mensagem duplicada se você habilitar a des duplicação ao exportar os resultados da pesquisa. As mensagens duplicadas terão um valor na coluna **ItemId pai** que identifica a mensagem como uma duplicata. O valor na **coluna ItemId pai** é o mesmo da coluna **Item DocumentId** da mensagem que foi exportada. 
    
    Para documentos de SharePoint sites OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:
    
  - A URL para o documento.
    
  - A URL para o conjunto de sites onde o documento está localizado.
    
  - A data em que o documento foi modificado pela última vez.
    
  - O nome do documento (que está localizado na coluna Assunto no log de resultados).
    
- **Manifest.xml** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa. As informações neste relatório são as mesmas do relatório de Results.csv, mas estão no formato especificado pelo Modelo de Referência de Descoberta Eletrônica (EDRM). Para obter mais informações sobre o EDRM, vá para [https://www.edrm.net](https://www.edrm.net) .
    
 **Quando devo desabilitar a exportação desses relatórios?**
  
Depende de suas necessidades específicas. Muitas organizações não exigem informações adicionais sobre os resultados da pesquisa e não precisam desses relatórios.
  
 **Em qual computador devo fazer isso?**
  
 Você precisa alterar a configuração do Registro em qualquer computador local em que você execute a ferramenta Exportar Descoberta e. 
  
 **Depois de alterar essa configuração, preciso reiniciar o computador?**
  
Não, você não precisa reiniciar o computador. Porém, se a ferramenta Exportação de Descoberta Digital estiver em execução, você terá que fechar e reinicie-a depois de alterar a configuração do Registro.
  
 **Uma chave existente do Registro é editada ou uma nova chave é criada?**
  
Uma nova chave do Registro é criada na primeira vez que você executar o arquivo .reg que você criou no procedimento neste tópico. Em seguida, a configuração é editada sempre que você alterar e executar o arquivo de edição .reg.
