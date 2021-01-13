---
title: Aplicar o IrM (Gerenciamento de Direitos de Informação) a uma lista ou biblioteca
f1.keywords:
- NOCSH
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
description: Você pode usar o Gerenciamento de Direitos de Informação (IRM) para ajudar a controlar e proteger arquivos baixados de listas ou bibliotecas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5b0b541619e7bd969072755eacf103d53da6fc6a
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840522"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Aplicar o IrM (Gerenciamento de Direitos de Informação) a uma lista ou biblioteca

Você pode usar o Gerenciamento de Direitos de Informação (IRM) para ajudar a controlar e proteger arquivos baixados de listas ou bibliotecas.
  
## <a name="administrator-preparations-before-applying-irm"></a>Preparação do administrador antes de aplicar o IRM

- O serviço Azure Rights Management (Azure RMS) da Proteção de Informações do Azure e o AD RMS (Active Directory Rights Management Services) local suportam o Gerenciamento de Direitos de Informação para sites. Nenhuma instalação separada ou adicional é necessária.

- Antes de aplicar o IRM a uma lista ou biblioteca, você precisa habilitar o IRM para seu site. Você precisará de permissões de administrador para habilitar o IRM.

- Para aplicar o IRM a uma lista ou biblioteca, você deve ter permissões de administrador para essa lista ou biblioteca.

- Se você estiver usando o SharePoint Online, os usuários poderão passar por tempos finais ao baixar arquivos maiores protegidos por IRM. Para evitar tempos, use seus programas do Office para aplicar proteção de IRM e armazene arquivos maiores em uma biblioteca do SharePoint que não use IRM.

> [!NOTE]
> Se você estiver usando o SharePoint Server 2013, um administrador de servidor deverá instalar protetores em todos os servidores Web front-end para cada tipo de arquivo que as pessoas em sua organização querem proteger usando o IRM.
  
## <a name="apply-irm-to-a-list-or-library"></a>Aplicar IRM a uma lista ou biblioteca
<a name="__toc256598179"> </a>

![Configurações de Gerenciamento de Direitos de Informação](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Vá para a lista ou biblioteca para a qual você deseja configurar o IRM.

2. Na faixa de opções, selecione **a guia Biblioteca** e, em seguida, selecione **Configurações da Biblioteca.** (Se você estiver trabalhando em uma  lista, selecione a guia Lista e, em seguida, selecione **Configurações de Lista).**
    
    ![Botões de Configurações da Biblioteca do SharePoint na Faixa de Opções](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. Em **Permissões e Gerenciamento, selecione** Gerenciamento de Direitos de **Informação.** Se o link Gerenciamento de Direitos de Informação não aparecer, talvez o IRM não seja habilitado para seu site. Entre em contato com o administrador do servidor para ver se você pode habilitar o IRM para seu site. O link **Gerenciamento de Direitos** de Informação não é exibido para bibliotecas de imagens.

4. Na página **Configurações de** Gerenciamento de Direitos de Informação, marque a caixa de seleção Restringir permissão a documentos nesta biblioteca no **download** para aplicar permissão restrita a documentos baixados pelos usuários desta lista ou biblioteca.

5. Na caixa **Criar um título de política de permissão,** insira um nome descritivo para a política. Use um nome que o ajude a identificar essa política a partir de outras políticas. Por exemplo, use **o Confidencial da** Empresa para aplicar permissões restritas a uma lista ou biblioteca que contenha documentos confidenciais da empresa.

6. Na caixa **Adicionar uma descrição de** política de permissão, digite uma descrição que aparecerá para as pessoas que usam essa lista ou biblioteca que explica como elas devem lidar com os documentos nessa lista ou biblioteca. Por exemplo, você pode **digitar** Discutir o conteúdo deste documento somente com outros funcionários se quiser restringir o acesso às informações desses documentos para funcionários internos. 

7. Para aplicar restrições adicionais aos documentos nesta lista ou biblioteca, selecione **Mostrar** Opções e faça o seguinte:

|**Para fazer isso:**|**Faça isso:**|
|:-----|:-----|
|Permitir que as pessoas imprimam documentos dessa lista ou biblioteca|Marque a **caixa de seleção Permitir que os visualizadores imprimam.**|
|Permitir que pessoas com pelo menos a permissão Exibir Itens executem código incorporado ou macros em um documento.|Marque a **caixa de seleção Permitir que os visualizadores executem scripts** e leitor de tela para funcionarem em documentos baixados. Se você selecionar essa opção, os usuários poderão executar código para extrair o conteúdo de um documento.           |
|Selecione essa opção se quiser restringir o acesso ao conteúdo a um período de tempo especificado. Se você selecionar essa opção, as licenças de emissão de pessoas para acessar o conteúdo expirará após o número especificado de dias, e as pessoas deverão retornar ao servidor para verificar suas credenciais e baixar uma nova cópia.|Marque a caixa de seleção Após o download, os direitos de acesso ao documento expiram após esse número de dias **(1 a 365) e especifique** o número de dias para os quais você deseja que o documento seja visualizado.|
| Impedir que as pessoas carreguem documentos que não suportam IRM nessa lista ou biblioteca. Se você selecionar essa opção, as pessoas não poderão carregar nenhum dos seguintes tipos de arquivo: tipos de arquivo que não tenham protetores de IRM correspondentes instalados em todos os servidores web front-end. Tipos de arquivo que o SharePoint Server 2010 não pode descriptografar. Tipos de arquivo protegidos por IRM em outro programa.|Marque a **caixa de seleção Não permitir que os usuários carreguem documentos que não suportam IRM.**|
|Remova permissões restritas dessa lista ou biblioteca em uma data específica.|Marque a caixa de seleção Parar **de restringir** o acesso à biblioteca e selecione a data que você deseja.|
|Controlar o intervalo em que as credenciais são armazenadas em cache para o programa licenciado para abrir o documento. Essa configuração só é suportada na nuvem global da Microsoft. A configuração não está disponível em implantações de nuvem nacional.|Marque a caixa de seleção Usuários que devem verificar suas credenciais usando esse intervalo **(dias)** e, em seguida, insira o intervalo para armazenamento em cache de credenciais em número de dias.|
|Permitir proteção de grupo para que os usuários possam compartilhar com membros do mesmo grupo.|Selecione **Permitir proteção de** grupo e insira o nome do grupo para compartilhamento.|

8. Depois de terminar de selecionar as opções que você deseja, selecione **OK**.
  
## <a name="what-is-information-rights-management"></a>O que é o Gerenciamento de Direitos de Informação?
<a name="__toc256598175"> </a>

O Gerenciamento de Direitos de Informação (IRM) permite limitar as ações que os usuários podem realizar em arquivos baixados de listas ou bibliotecas. O IRM criptografa os arquivos baixados e limite o conjunto de usuários e programas que podem descriptografar estes arquivos. O IRM também pode limitar os direitos dos usuários que podem ler arquivos, para que eles não possam tomar ações como imprimir cópias dos arquivos ou copiar o texto.
  
Você pode usar o IRM em listas ou bibliotecas para limitar a disseminação de conteúdos confidenciais. Por exemplo, se você estiver criando uma biblioteca de documentos para compartilhar informações sobre os próximos produtos com representantes de marketing selecionados, poderá usar o IRM para impedir que esses indivíduos compartilhem esse conteúdo com outros funcionários da empresa.
  
Em um site, você aplica o IRM a uma lista ou biblioteca inteira, em vez de a arquivos individuais. Isso facilita a garantia de um nível consistente de proteção para todo um conjunto de documentos ou arquivos. Assim, o IRM pode ajudar sua organização a impor políticas corporativas que regem o uso e a disseminação de informações confidenciais ou proprietárias.
  
> [!NOTE]
> As informações nesta página sobre o Gerenciamento de Direitos de Informação são sobresitutas em todos os termos que referenciam o "Gerenciamento de Direitos de Informação" em quaisquer contratos de termos de licença do Microsoft SharePoint Server 2013 e do SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Como o IRM pode ajudar a proteger o conteúdo
<a name="__toc256598176"> </a>

O IRM ajuda a proteger o conteúdo restrito das seguintes maneiras:
  
- Ajuda a impedir que um visualizador autorizado copie, modifique, imprindo, envie fax ou copie e copie o conteúdo para uso não autorizado
    
- Ajuda a impedir que um visualizador autorizado copie o conteúdo usando o recurso Imprimir Tela no Microsoft Windows
    
- Ajuda a impedir que um visualizador não autorizado veja o conteúdo se ele for enviado por email depois que ele for baixado do servidor
    
- Restringe o acesso ao conteúdo a um período de tempo especificado, após o qual os usuários devem confirmar suas credenciais e baixar o conteúdo novamente
    
- Ajuda a impor políticas corporativas que regem o uso e a disseminação de conteúdo em sua organização
    
### <a name="how-irm-cannot-help-protect-content"></a>Como o IRM não pode ajudar a proteger o conteúdo
<a name="__toc256598177"> </a>

O IRM não pode proteger o conteúdo restrito do seguinte:
  
- Eliminação, roubo, captura ou transmissão por programas mal-intencionados, como a captura de Troia, os agentes de digitação e determinados tipos de spyware
    
- Perda ou corrupção devido às ações de vírus do computador
    
- Copiar ou retipar manualmente o conteúdo da exibição em uma tela
    
- Fotografia digital ou de filme do conteúdo exibido em uma tela
    
- Copiando o uso de programas de captura de tela de terceiros
    
- Cópia de metadados de conteúdo (valores de coluna) por meio do uso de programas de captura de tela de terceiros ou ação de copiar e colar
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Como o IRM funciona para listas e bibliotecas
<a name="__toc256598178"> </a>

A proteção por IRM é aplicada a arquivos no nível de lista ou biblioteca. Quando o IRM está habilitado para uma biblioteca, o gerenciamento de direitos se aplica a todos os arquivos nessa biblioteca. Quando o IRM está habilitado para uma lista, o gerenciamento de direitos se aplica somente aos arquivos anexados a itens de lista, não aos itens de lista reais.
  
Quando as pessoas baixam arquivos em uma lista ou biblioteca habilitada para IRM, os arquivos são criptografados para que somente pessoas autorizadas possam exibi-los. Cada arquivo com direitos gerenciados também contém uma licença de emissão que impõe restrições às pessoas que visualizam o arquivo. As restrições típicas incluem tornar um arquivo somente leitura, desabilitar a cópia de texto, impedir que as pessoas salvam uma cópia local e impedir que as pessoas imprimi-lo. Programas cliente que podem ler tipos de arquivo com suporte para IRM usam a licença de emissão no arquivo com direitos gerenciados para impor essas restrições. É assim que um arquivo com direitos gerenciados mantém sua proteção mesmo depois de ser baixado do servidor.
  
Os tipos de restrições que são aplicadas a um arquivo quando ele é baixado de uma lista ou biblioteca são baseados nas permissões do usuário individual no site que contém o arquivo. A tabela a seguir explica como as permissões em sites correspondem às permissões do IRM.
  
|**Permissões**|**Permissões do IRM**|
|:-----|:-----|
|Gerenciar Permissões, Gerenciar Site|**Controle total** (conforme definido pelo programa cliente): essa permissão geralmente permite que um usuário leia, edite, copie, salve e modifique permissões de conteúdo com direitos gerenciados.|
|Editar Itens, Gerenciar Listas, Adicionar e Personalizar Páginas|**Editar**, **Copiar** e **Salvar:** um usuário só  poderá imprimir um arquivo se a caixa de seleção Permitir que os usuários imprimam documentos está marcada na página Configurações de Gerenciamento de Direitos de Informação da lista ou biblioteca.|
|Exibir Itens|**Leitura:** um usuário pode ler o documento, mas não pode copiar ou modificar seu conteúdo. Um usuário só poderá  imprimir se a caixa de seleção Permitir que os usuários imprimam documentos estiver marcada na página Configurações de Gerenciamento de Direitos de Informação da lista ou biblioteca.|
|Outros|Nenhuma outra permissão corresponde diretamente às permissões do IRM.|
   
Quando você habilita o IRM para uma lista ou biblioteca no SharePoint Server 2013, só pode proteger os tipos de arquivo nessa lista ou biblioteca para a qual um protetor é instalado em todos os servidores Web front-end. Um protetor é um programa que controla a criptografia e a descriptografia de arquivos gerenciados por direitos de um formato de arquivo específico. O SharePoint inclui protetores para os seguintes tipos de arquivo:
  
- Formulários do Microsoft Office InfoPath
    
- Os formatos de arquivo 97-2003 para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- Os formatos Office Open XML para os seguintes programas do Microsoft Office: Word, Excel e PowerPoint
    
- O formato XML Paper Specification (XPS)
    
Se sua organização planeja usar o IRM para proteger qualquer outro tipo de arquivo além daqueles listados acima, o administrador do servidor deve instalar protetores para esses formatos de arquivo adicionais.
  

