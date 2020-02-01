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
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Edite o registro do Windows no computador local para desabilitar relatórios ao exportar os resultados de uma pesquisa de conteúdo do centro de conformidade de & de segurança no Office 365. A desabilitação desses relatórios pode acelerar o tempo de download e poupar espaço em disco.
ms.openlocfilehash: 99f8079bdbb0a3a43d0306dcf6b6ca8ab2c4fbef
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595236"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo

Ao usar a ferramenta de exportação de descoberta eletrônica do Office 365 para exportar os resultados de uma pesquisa de conteúdo no centro de conformidade de & de segurança, a ferramenta cria e exporta automaticamente dois relatórios que contêm informações adicionais sobre o conteúdo exportado. Esses relatórios são o arquivo Results. csv e o arquivo manifest. XML (consulte a seção [perguntas frequentes sobre a desabilitação de relatórios de exportação](#frequently-asked-questions-about-disabling-export-reports) neste tópico para obter descrições detalhadas desses relatórios). Como esses arquivos podem ser muito grandes, você pode acelerar o tempo de download e poupar espaço em disco, impedindo que esses arquivos sejam exportados. Você pode fazer isso alterando o registro do Windows no computador que você usa para exportar os resultados da pesquisa. Se você quiser incluir os relatórios mais tarde, poderá editar a configuração do registro. 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>Criar configurações do registro para desabilitar os relatórios de exportação

Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.
  
1. Feche a ferramenta de exportação de descoberta eletrônica do Office 365 se ela estiver aberta.
    
2. Execute uma ou ambas as etapas a seguir, dependendo do relatório de exportação que você deseja desabilitar.
    
    - **Results. csv**
    
      Salve o seguinte texto em um arquivo de registro do Windows usando um sufixo de nome de arquivo. reg; por exemplo, DisableResultsCsv. reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest. xml**
    
      Salve o seguinte texto em um arquivo de registro do Windows usando um sufixo de nome de arquivo. reg; por exemplo, DisableManifestXml. reg.
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. No Windows Explorer, clique ou clique duas vezes no arquivo. reg que você criou nas etapas anteriores.
    
4. Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração. 
    
5. Quando for solicitado a continuar, clique em **Sim**.
    
    O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>Editar configurações do registro para habilitar novamente os relatórios de exportação

Se você desabilitou os relatórios Results. csv e manifest. XML criando os arquivos. reg no procedimento anterior, poderá editar esses arquivos para reabilitar um relatório para que ele seja exportado com os resultados da pesquisa. Novamente, execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.
  
1. Feche a ferramenta de exportação de descoberta eletrônica do Office 365 se ela estiver aberta.
    
2. Edite um ou ambos os arquivos. reg Edit que você criou no procedimento anterior.
    
    - **Results. csv**
    
        Abra o arquivo DisableResultsCsv. reg no bloco de notas, altere `False` o `True`valor para e salve o arquivo. Por exemplo, após editar o arquivo, ele terá a seguinte aparência:
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest. xml**
    
        Abra o arquivo DisableManifestXml. reg no bloco de notas, altere `False` o `True`valor para e salve o arquivo. Por exemplo, após editar o arquivo, ele terá a seguinte aparência:
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. No Windows Explorer, clique ou clique duas vezes em um arquivo. reg que você editou na etapa anterior.
    
4. Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração. 
    
5. Quando for solicitado a continuar, clique em **Sim**.
    
    O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>Perguntas frequentes sobre a desabilitação de relatórios de exportação

 **Quais são os relatórios Results. csv e manifest. xml?**
  
Os arquivos Results. csv e manifest. xml contêm informações adicionais sobre o conteúdo que foi exportado.
  
- **Results. csv** um documento do Excel que contém informações sobre cada item que é baixado como resultado da pesquisa. Para emails, o log do resultado contém informações sobre cada mensagem, incluindo: 
    
  - O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).
    
  - A data na qual a mensagem foi enviada ou recebida.
    
  - A linha de assunto da mensagem.
    
  - O remetente e os destinatários da mensagem.
    
  - Se a mensagem é uma mensagem duplicada se você habilitou a eliminação de duplicação ao exportar os resultados da pesquisa. As mensagens duplicadas terão um valor na coluna **ItemId pai** que identifica a mensagem como uma duplicata. O valor na coluna **ItemId pai** é o mesmo que o valor da coluna **DocumentID de item** da mensagem que foi exportada. 
    
    Para documentos de sites do SharePoint e do OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:
    
  - A URL para o documento.
    
  - A URL para o conjunto de sites onde o documento está localizado.
    
  - A data em que o documento foi modificado pela última vez.
    
  - O nome do documento (que está localizado na coluna Assunto no log de resultados).
    
- **Manifest. xml** um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa. As informações neste relatório são as mesmas do relatório Results. csv, mas estão no formato especificado pelo modelo de referência de descoberta eletrônica (EDRM). Para obter mais informações sobre o EDRM, [https://www.edrm.net](https://www.edrm.net)acesse.
    
 **Quando devo desabilitar a exportação desses relatórios?**
  
Depende de suas necessidades específicas. Muitas organizações não exigem informações adicionais sobre os resultados da pesquisa e não precisam desses relatórios.
  
 **Em qual computador tenho que fazer isso?**
  
 Você precisa alterar a configuração do registro em qualquer computador local em que executa a ferramenta de exportação de descoberta eletrônica do Office 365. 
  
 **Após alterar essa configuração, preciso reiniciar o computador?**
  
Não, não é necessário reiniciar o computador. Mas, se a ferramenta de exportação de descoberta eletrônica do Office 365 estiver em execução, você terá que fechá-la e reiniciá-la depois de alterar a configuração do registro.
  
 **Uma chave de registro existente é editada ou faz uma nova chave ser criada?**
  
Uma nova chave de registro é criada na primeira vez que você executa o arquivo. reg que você criou no procedimento deste tópico. Em seguida, a configuração será editada sempre que você alterar e executar novamente o arquivo. reg Edit.
