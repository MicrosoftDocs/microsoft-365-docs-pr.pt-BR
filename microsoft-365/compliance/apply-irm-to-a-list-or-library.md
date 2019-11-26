---
title: Aplicar o gerenciamento de direitos de informação (IRM) a uma lista ou biblioteca
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: Você pode usar o gerenciamento de direitos de informação (IRM) para ajudar a controlar e proteger arquivos baixados de listas ou bibliotecas.
ms.openlocfilehash: cd970f5e89a08de133511c99b8209b389f32cd87
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256808"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Aplicar o gerenciamento de direitos de informação (IRM) a uma lista ou biblioteca

Você pode usar o gerenciamento de direitos de informação (IRM) para ajudar a controlar e proteger arquivos baixados de listas ou bibliotecas.
  
## <a name="before-you-begin"></a>Antes de começar

- O serviço Azure Rights Management (Azure RMS) da proteção de informações do Azure e o equivalente local, o Active Directory Rights Management Services (AD RMS), oferecem suporte ao gerenciamento de direitos de informação para sites. Nenhuma instalação separada ou adicional é necessária.
    
- Antes de aplicar o IRM a uma lista ou biblioteca, ele deve primeiro ser habilitado por um administrador do site.
    
- Para aplicar o IRM a uma lista ou biblioteca, você deve ter permissões de administrador para a lista ou biblioteca.
    
- Se você estiver usando o SharePoint Online, os usuários poderão experimentar tempos limite ao baixar arquivos maiores protegidos por IRM. Se isso acontecer, aplique a proteção de IRM usando os programas do Office e armazene arquivos maiores em uma biblioteca do SharePoint que não use o IRM.
    
> [!NOTE]
> Se você estiver usando o SharePoint Server 2013, um administrador de servidor deverá instalar os protetores em todos os servidores Web front-end para cada tipo de arquivo que as pessoas em sua organização quiserem proteger usando o IRM. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Aplicar o IRM a uma lista ou biblioteca
<a name="__toc256598179"> </a>

![Configurações de gerenciamento de direitos de informação](media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Vá para a lista ou biblioteca para a qual você deseja configurar o IRM.
    
2. Na faixa de opções, clique na guia **biblioteca** e, em seguida, clique em **configurações da biblioteca**. (Se você estiver trabalhando em uma lista, clique na guia **lista** e, em seguida, clique em **configurações de lista**).
    
    ![Botões de configurações da biblioteca do SharePoint na faixa de opções](media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. Em **permissões e gerenciamento**, clique em **Gerenciamento de direitos de informação**. Se o link de gerenciamento de direitos de informação não aparecer, o IRM pode não estar habilitado para seu site. Entre em contato com o administrador do servidor para ver se é possível habilitar o IRM para seu site. O link de gerenciamento de direitos de informação não aparece para bibliotecas de imagens.
    
4. Na página **configurações de gerenciamento de direitos de informação** , marque a caixa de seleção **restringir a permissão para documentos nesta biblioteca ao baixar** , para aplicar permissão restrita a documentos baixados dessa lista ou biblioteca. 
    
5. Na caixa **criar um título de política de permissão** , digite um nome descritivo para a política que você pode usar posteriormente para diferenciar essa política de outras políticas. Por exemplo, você pode digitar **confidencial da empresa** se estiver aplicando permissão restrita a uma lista ou biblioteca que conterá documentos da empresa confidenciais. 
    
6. Na caixa **Adicionar uma descrição de política de permissão** , digite uma descrição que será exibida para pessoas que usam esta lista ou biblioteca que explica como elas devem lidar com os documentos nesta lista ou biblioteca. Por exemplo, você pode digitar **discutir o conteúdo deste documento somente com outros funcionários** se quiser restringir o acesso às informações desses documentos a funcionários internos. 
    
7. Para aplicar restrições adicionais aos documentos nesta lista ou biblioteca, clique em **Mostrar opções**e siga um destes procedimentos:
    
|**Para fazer isso:**|**Faça o seguinte:**|
|:-----|:-----|
|Permitir que as pessoas imprimam documentos desta lista ou biblioteca  <br/> |Marque a caixa de seleção **permitir que os visualizadores imprimam** .  <br/> |
|Permita que as pessoas com pelo menos a permissão Exibir itens executem código incorporado ou macros em um documento.  <br/> |Selecione a caixa de seleção **permitir que os visualizadores executem scripts e leitor de tela para funcionar em documentos baixados** .  <br/> Se você selecionar essa opção, os usuários poderão executar o código para extrair o conteúdo de um documento.           |
|Exigir que as pessoas verifiquem suas credenciais em intervalos específicos.  <br/> Selecione essa opção se você quiser restringir o acesso ao conteúdo para um período especificado de tempo. Se você selecionar essa opção, as licenças de publicação de pessoas para acessar o conteúdo expirarão após o número de dias especificado e as pessoas serão solicitadas a retornar ao servidor para verificar suas credenciais e baixar uma nova cópia.  <br/> |Marque a caixa de seleção **os usuários devem verificar suas credenciais usando este intervalo (dias)** e especifique o número de dias em que você deseja que o documento seja exibido.  <br/> |
| Impedir que as pessoas carreguem documentos que não dão suporte ao IRM para esta lista ou biblioteca.  <br/>  Se você selecionar essa opção, as pessoas não poderão carregar nenhum dos seguintes tipos de arquivo:  <br/>  Tipos de arquivo que não têm protetores de IRM correspondentes instalados em todos os servidores Web front-end.  <br/>  Tipos de arquivo que o SharePoint Server 2010 não pode descriptografar.  <br/>  Tipos de arquivo que estão protegidos por IRM em outro programa  <br/> |Marque a caixa de seleção não **permitir que os usuários carreguem documentos que não dão suporte ao IRM** .  <br/> |
|Remover permissões restritas dessa lista ou biblioteca em uma data específica.  <br/> |Marque a caixa de seleção **parar de restringir o acesso à biblioteca em** e selecione a data desejada.  <br/> |
|Controle o intervalo em que as credenciais são armazenadas em cache para o programa licenciado para abrir o documento.  <br/> |No **intervalo de definir credenciais e proteção de grupo**, insira o intervalo de credenciais de cache em número de dias.  <br/> |
|Permitir proteção de grupo para que os usuários possam compartilhar com membros do mesmo grupo.  <br/> |Selecione **permitir proteção de grupo**e digite o nome do grupo para compartilhamento.  <br/> |
   
8. Após concluir a seleção das opções desejadas, clique em **OK**.
  
## <a name="what-is-information-rights-management"></a>O que é gerenciamento de direitos de informação?
<a name="__toc256598175"> </a>

O gerenciamento de direitos de informação (IRM) permite limitar as ações que os usuários podem executar em arquivos que foram baixados de listas ou bibliotecas. O IRM criptografa os arquivos baixados e limite o conjunto de usuários e programas que podem descriptografar estes arquivos. O IRM também pode limitar os direitos dos usuários que podem ler arquivos, para que eles não possam tomar ações como imprimir cópias dos arquivos ou copiar o texto.
  
Você pode usar o IRM em listas ou bibliotecas para limitar a disseminação de conteúdo confidencial. Por exemplo, se você estiver criando uma biblioteca de documentos para compartilhar informações sobre produtos futuros com representantes de marketing selecionados, você pode usar o IRM para impedir que essas pessoas compartilhem esse conteúdo com outros funcionários da empresa.
  
Em um site, você aplica o IRM a uma lista ou biblioteca inteira, e não a arquivos individuais. Isso facilita a garantia de um nível consistente de proteção para um conjunto completo de documentos ou arquivos. Portanto, o IRM pode ajudar sua organização a impor políticas corporativas que regem o uso e a disseminação de informações confidenciais ou proprietárias.
  
> [!NOTE]
> As informações nesta página sobre o gerenciamento de direitos de informação substituem quaisquer termos que fazem referência ao "gerenciamento de direitos de informação" em qualquer contrato de licença do Microsoft SharePoint Server 2013 e do SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Como o IRM pode ajudar a proteger o conteúdo
<a name="__toc256598176"> </a>

O IRM ajuda a proteger o conteúdo restrito das seguintes maneiras:
  
- Ajuda a evitar que um visualizador autorizado copie, modifique, imprima, envie por fax ou copie e cole o conteúdo para uso não autorizado
    
- Ajuda a evitar que um visualizador autorizado Copie o conteúdo usando o recurso Print Screen no Microsoft Windows
    
- Ajuda a impedir que um visualizador não autorizado exiba o conteúdo se for enviado por email após o download do servidor
    
- Restringe o acesso ao conteúdo para um período de tempo especificado, após o qual os usuários devem confirmar suas credenciais e baixar o conteúdo novamente
    
- Ajuda a impor políticas corporativas que regem o uso e a disseminação de conteúdo dentro da sua organização
    
### <a name="how-irm-cannot-help-protect-content"></a>Como o IRM não pode ajudar a proteger o conteúdo
<a name="__toc256598177"> </a>

O IRM não pode proteger o conteúdo restrito do seguinte:
  
- Eliminação, roubo, captura ou transmissão por programas mal-intencionados, como cavalos de Tróia, registradores de teclas e certos tipos de spyware
    
- Perda ou corrupção devido às ações de vírus de computador
    
- Cópia manual ou redigitação de conteúdo da exibição em uma tela
    
- Fotografia digital ou de filme de conteúdo que é exibido em uma tela
    
- Copiando por meio do uso de programas de captura de tela de terceiros
    
- Cópia de metadados de conteúdo (valores de coluna) por meio do uso de programas de captura de tela de terceiros ou ação de copiar e colar
    
[Aplicar o Gerenciamento de Direitos de Informação a uma lista ou biblioteca](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Como o IRM funciona para listas e bibliotecas
<a name="__toc256598178"> </a>

A proteção de IRM é aplicada aos arquivos no nível de lista ou biblioteca. Quando o IRM está habilitado para uma biblioteca, o gerenciamento de direitos se aplica a todos os arquivos nessa biblioteca. Quando o IRM está habilitado para uma lista, o gerenciamento de direitos aplica-se somente aos arquivos anexados a itens de lista, e não aos itens de lista reais.
  
Quando as pessoas baixam arquivos em uma lista ou biblioteca habilitada para IRM, os arquivos são criptografados para que apenas pessoas autorizadas possam exibi-los. Cada arquivo gerenciado por direitos também contém uma licença de publicação que impõe restrições às pessoas que exibem o arquivo. As restrições típicas incluem tornar um arquivo somente leitura, desabilitar a cópia de texto, impedir que as pessoas salvem uma cópia local e impedindo que as pessoas imprimam o arquivo. Os programas cliente que podem ler tipos de arquivo com suporte para IRM usam a licença de publicação dentro do arquivo gerenciado por direitos para impor essas restrições. É assim que um arquivo gerenciado por direitos mantém sua proteção mesmo depois de ser baixado do servidor.
  
Os tipos de restrições que são aplicadas a um arquivo quando ele é baixado de uma lista ou biblioteca são baseados nas permissões do usuário individual no site que contém o arquivo. A tabela a seguir explica como as permissões nos sites correspondem às permissões do IRM.
  
|**Permissões**|**Permissões de IRM**|
|:-----|:-----|
|Gerenciar permissões, gerenciar site da Web  <br/> |**Controle total** (conforme definido pelo programa cliente): essa permissão geralmente permite que um usuário leia, edite, copie, salve e modifique permissões de conteúdo gerenciado por direitos.  <br/> |
|Editar itens, gerenciar listas, adicionar e personalizar páginas  <br/> |**Editar**, **copiar**e **salvar**: um usuário pode imprimir um arquivo somente se a caixa de seleção **permitir que os usuários imprimam documentos** estiver marcada na página Configurações de gerenciamento de direitos de informação para a lista ou biblioteca.  <br/> |
|Exibir Itens  <br/> |**Leitura**: um usuário pode ler o documento, mas não pode copiar nem modificar seu conteúdo. Um usuário pode imprimir somente se a caixa de seleção **permitir que os usuários imprimam documentos** estiver marcada na página Configurações de gerenciamento de direitos de informação da lista ou biblioteca.  <br/> |
|Other  <br/> |Nenhuma outra permissão corresponde diretamente às permissões de IRM.  <br/> |
   
Ao habilitar o IRM para uma lista ou biblioteca no SharePoint Server 2013, você só pode proteger tipos de arquivo nessa lista ou biblioteca para a qual um protetor está instalado em todos os servidores Web front-end. Um protetor é um programa que controla a criptografia e a descriptografia de arquivos gerenciados por direitos de um formato de arquivo específico. O SharePoint inclui protetores para os seguintes tipos de arquivo:
  
- Formulários do Microsoft Office InfoPath
    
- Os formatos de arquivo 97-2003 para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- Formatos do Office Open XML para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- O formato XML Paper Specification (XPS)
    
Se sua organização planeja usar o IRM para proteger qualquer outro tipo de arquivo além dos listados acima, o administrador do servidor deve instalar protetores para esses formatos de arquivo adicionais.
  

