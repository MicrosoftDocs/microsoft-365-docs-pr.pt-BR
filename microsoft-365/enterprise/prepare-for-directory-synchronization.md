---
title: Preparar-se para a sincronização de diretórios com o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descreve como se preparar para provisionar usuários para o Microsoft 365 usando a sincronização de diretórios e os benefícios a longo prazo do uso desse método.
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371619"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Preparar-se para a sincronização de diretórios com o Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Os benefícios da sincronização híbrida de identidade e diretórios em sua organização incluem:

- Reduzir os programas administrativos em sua organização
- Opcionalmente, habilitando o cenário de single sign-on
- Automatizando alterações de conta no Microsoft 365

Para saber mais sobre as vantagens de usar a sincronização de diretórios, confira a identidade híbrida com o [Azure Active Directory (Azure AD)](https://go.microsoft.com/fwlink/p/?LinkId=525398) e a identidade híbrida do [Microsoft 365.](plan-for-directory-synchronization.md)

No entanto, a sincronização de diretório requer planejamento e preparação para garantir que seus Serviços de Domínio do Active Directory (AD DS) sincronizam com o locatário do Azure AD da sua assinatura do Microsoft 365 com um mínimo de erros.

Siga estas etapas para obter os melhores resultados.

## <a name="1-directory-cleanup-tasks"></a>1. Tarefas de limpeza de diretório

Antes de sincronizar o AD DS com seu locatário do Azure AD, você precisa limpar o AD DS.

> [!IMPORTANT]
> Se você não executar a limpeza do AD DS antes de sincronizar, isso pode levar a um impacto negativo significativo no processo de implantação. Pode levar dias ou até mesmo semanas para passar pelo ciclo de sincronização de diretórios, identificação de erros e ressincronização.

No AD DS, conclua as seguintes tarefas de limpeza para cada conta de usuário que receberá uma licença do Microsoft 365:

1. Certifique-se de um endereço de email válido e exclusivo no **atributo proxyAddresses.**

2. Remova quaisquer valores duplicados no **atributo proxyAddresses.**

3. Se possível, certifique-se de um valor válido e exclusivo para o **atributo userPrincipalName** no objeto de **usuário do** usuário. Para ter a melhor experiência de sincronização, verifique se o UPN do AD DS corresponde ao UPN do Azure AD. Se um usuário não tiver um valor para o atributo  **userPrincipalName,** o objeto de usuário deverá conter um valor válido e exclusivo para o **atributo sAMAccountName.** Remova quaisquer valores duplicados no **atributo userPrincipalName.**

4. Para o uso ideal da GAL (lista de endereços global), verifique se as informações nos seguintes atributos da conta de usuário do AD DS estão corretas:

   - givenName
   - surname
   - displayName
   - Cargo
   - Departamento
   - Escritório
   - Telefone comercial
   - Telefone celular
   - Número do fax
   - Endereço
   - Cidade
   - Estado
   - CEP
   - País

## <a name="2-directory-object-and-attribute-preparation"></a>2. Preparação de atributo e objeto de diretório

A sincronização de diretórios bem-sucedida entre o AD DS e o Microsoft 365 requer que seus atributos do AD DS estejam preparados corretamente. Por exemplo, você precisa garantir que caracteres específicos não sejam usados em determinados atributos sincronizados com o ambiente do Microsoft 365. Caracteres inesperados não causam falha na sincronização de diretórios, mas podem retornar um aviso. Caracteres inválidos causarão falha na sincronização de diretórios.

A sincronização de diretórios também falhará se alguns dos seus usuários do AD DS têm um ou mais atributos duplicados. Cada usuário deve ter atributos exclusivos.

Os atributos que você precisa preparar estão listados aqui:

- **displayName**

  - Se o atributo existir no objeto user, ele será sincronizado com o Microsoft 365.
  - Se esse atributo existir no objeto de usuário, deverá haver um valor para ele. Ou seja, o atributo não deve estar em branco.
  - Número máximo de caracteres: 256

- **givenName**

  - Se o atributo existir no objeto do usuário, ele será sincronizado com o Microsoft 365, mas o Microsoft 365 não o exige nem usa.
  - Número máximo de caracteres: 64

- **email**

  - O valor do atributo deve ser exclusivo dentro do diretório.

    > [!NOTE]
    > Se houver valores duplicados, o primeiro usuário com o valor será sincronizado. Os usuários subsequentes não aparecerão no Microsoft 365. Você deve modificar o valor no Microsoft 365 ou modificar os dois valores no AD DS para que ambos os usuários apareçam no Microsoft 365.

- **mailNickname** (alias do Exchange)

  - O valor do atributo não pode começar com um ponto (.).
  - O valor do atributo deve ser exclusivo dentro do diretório.

    > [!NOTE]
    > Sublinhado ("_") no nome sincronizado indica que o valor original desse atributo contém caracteres inválidos. Para obter mais informações sobre esse atributo, consulte o atributo [de alias do Exchange.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)
    >

- **proxyAddresses**

  - Atributo de vários valores
  - Número máximo de caracteres por valor: 256
  - O valor do atributo não deve conter um espaço.
  - O valor do atributo deve ser exclusivo dentro do diretório.
  - Caracteres \< \> inválidos: ( ) ; , [ ] " '

    Observe que os caracteres inválidos se aplicam aos caracteres após o delimidor de tipo e ":", de forma que SMTP:User@contso.com seja permitido, mas SMTP:user:M@contoso.com não é.

    > [!IMPORTANT]
    > Todos os endereços SMTP devem estar em conformidade com os padrões de mensagens de email. Remova endereços duplicados ou indesejados se eles existirem.

- **sAMAccountName**

  - Número máximo de caracteres: 20
  - O valor do atributo deve ser exclusivo dentro do diretório.
  - Caracteres inválidos: [ \ " | , / : \< \> + = ; ? \* ']
  - Se um usuário tiver um atributo **sAMAccountName** inválido, mas tiver um atributo **userPrincipalName** válido, a conta de usuário será criada no Microsoft 365.
  - Se **sAMAccountName** e **userPrincipalName são** inválidos, o atributo **userPrincipalName** do AD DS deve ser atualizado.

- **sn** (sobrenome)

  - Se o atributo existir no objeto do usuário, ele será sincronizado com o Microsoft 365, mas o Microsoft 365 não o exige nem usa.

- **targetAddress**

    É necessário que o atributo **targetAddress** (por exemplo, SMTP:tom@contoso.com) preenchido para o usuário apareça na GAL do Microsoft 365. Em cenários de migração de mensagens de terceiros, isso exigiria a extensão de esquema do Microsoft 365 para o AD DS. A extensão de esquema do Microsoft 365 também adicionaria outros atributos úteis para gerenciar objetos do Microsoft 365 preenchidos usando uma ferramenta de sincronização de diretórios do AD DS. Por exemplo, o **atributo msExchHideFromAddressLists** para gerenciar caixas de correio ou grupos de distribuição ocultos seria adicionado.

  - Número máximo de caracteres: 256
  - O valor do atributo não deve conter um espaço.
  - O valor do atributo deve ser exclusivo dentro do diretório.
  - Caracteres inválidos: \ \< \> ( ) ; , [ ] "
  - Todos os endereços SMTP devem estar em conformidade com os padrões de mensagens de email.

- **userPrincipalName**

  - O **atributo userPrincipalName** deve estar no formato de logon no estilo internet onde o nome de usuário é seguido pelo sinal de aa (@) e um nome de domínio: por exemplo, user@contoso.com. Todos os endereços SMTP devem estar em conformidade com os padrões de mensagens de email.
  - O número máximo de caracteres para o **atributo userPrincipalName** é 113. Um número específico de caracteres é permitido antes e depois do sinal de aa (@), da seguinte forma:
  - Número máximo de caracteres para o nome de usuário que está na frente do sinal de agosto (@): 64
  - Número máximo de caracteres para o nome de domínio após o sinal de agosto (@): 48
  - Caracteres inválidos: \ % &amp; \* + / = ? { } | \< \> ( ) ; : , [ ] "
  - Caracteres permitidos: A – Z, a - z, 0 – 9, ' . - _ ! # ^ ~
  - Letras com marcas diacríticas, como umlauts, acentos e tils, são caracteres inválidos.
  - O caractere @ é necessário em cada **valor userPrincipalName.**
  - O caractere @ não pode ser o primeiro caractere em cada **valor userPrincipalName.**
  - O nome de usuário não pode terminar com um ponto (.), um esão (),um espaço ou um &amp; sinal de a ponto (@).
  - O nome de usuário não pode conter espaços.
  - Domínios que podem ser usados; por exemplo, domínios locais ou internos não podem ser usados.
  - Unicode é convertido em caracteres de sublinhado.
  - **userPrincipalName** não pode conter valores duplicados no diretório.

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. Preparar o atributo userPrincipalName

O Active Directory foi projetado para permitir que os usuários finais em sua organização se inscrevam em seu diretório usando **sAMAccountName** ou **userPrincipalName**. Da mesma forma, os usuários finais podem entrar no Microsoft 365 usando o nome UPN de sua conta de trabalho ou de estudante. A sincronização de diretório tenta criar novos usuários no Azure Active Directory usando o mesmo UPN que está no AD DS. O UPN é formatado como um endereço de email.

No Microsoft 365, o UPN é o atributo padrão usado para gerar o endereço de email. É fácil obter **userPrincipalName** (no AD DS e no Azure AD) e o endereço de email principal em **proxyAddresses** definidos para valores diferentes. Quando eles são definidos com valores diferentes, pode haver confusão para administradores e usuários finais.

É melhor alinhar esses atributos para reduzir a confusão. Para atender aos requisitos de login único com os Serviços de Federação do Active Directory (AD FS) 2.0, você precisa garantir que os UPNs no Azure Active Directory e no AD DS sejam válidos e usem um namespace de domínio válido.

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. Adicionar um sufixo UPN alternativo ao AD DS

Talvez seja necessário adicionar um sufixo UPN alternativo para associar as credenciais corporativas do usuário ao ambiente do Microsoft 365. Um sufixo UPN é a parte do UPN à direita do caractere @. UPNs usados para logon único podem conter letras, números, pontos, traços e sublinhados, mas nenhum outro tipo de caracteres.

Para obter mais informações sobre como adicionar um sufixo UPN alternativo ao Active Directory, consulte [Preparar-se para a sincronização de diretórios.]( https://go.microsoft.com/fwlink/p/?LinkId=525430)

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. Corresponder o UPN do AD DS com o UPN do Microsoft 365

Se você já tiver definido a sincronização de diretórios, o UPN do usuário para o Microsoft 365 pode não corresponder ao UPN do AD DS do usuário definido em seu AD DS. Isso pode ocorrer quando uma licença foi atribuída ao usuário antes da verificação do domínio. Para corrigir isso, use o PowerShell para corrigir [o UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) duplicado para atualizar o UPN do usuário para garantir que o UPN do Microsoft 365 corresponde ao nome de usuário e domínio corporativos. Se você estiver atualizando o UPN no AD DS e quiser que ele seja sincronizado com a identidade do Azure Active Directory, será necessário remover a licença do usuário no Microsoft 365 antes de fazer as alterações no AD DS.

Consulte também [como preparar um domínio não-rouável (como o domínio .local) para sincronização de diretórios.](prepare-a-non-routable-domain-for-directory-synchronization.md)

## <a name="next-steps"></a>Próximas etapas

Se você tiver feito as etapas 1 a 5 acima, consulte [Configurar a sincronização de diretórios.](set-up-directory-synchronization.md)
