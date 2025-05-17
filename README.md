# NoCODE - NoCode - App de Controle de Estoque com AppSheet

Este aplicativo foi criado com AppSheet, utilizando planilhas do Google como base de dados. Ele permite:

- Cadastrar novos produtos
- Registrar entradas e saídas de itens
- Acompanhar o estoque atual

## 🧰 AppSheet?

- O AppSheet é uma plataforma do Google que permite criar aplicativos sem precisar programar. Ele usa planilhas como base de dados (por exemplo, Google Sheets) e permite que você crie apps interativos.

## Mão na Massa

### 1. Criando a planilha - Estrutura do banco de dados

- Acesse [Google Sheets](https://docs.google.com/spreadsheets/u/0/)

- [Modelo base para planilha](https://docs.google.com/spreadsheets/d/15sQM_PVVNq3_ubLMpVk3yrTjkf2NR2A1YBI_fsgiLKM/edit?usp=sharing)

## 2. Acesse o AppSheet
- Acesse o [AppSheet](https://www.appsheet.com)
- Clique em "Start" ou "Iniciar"
- Faça login com sua conta Google

![tela inicial do AppSheet após login](image.png)

## 3. Criando o App
- Clique em "Create"

![localizacao do botao create, para iniciar a criacao de um novo aplicativo](image-1.png)

- Escolha "App" > "Start with existing data" > "Nome do aplicativo e categoria" > "choose your data"

![indicacao para iniciar o aplicativo com uma tabela ja existente, após, solicitação do nome do aplicativo e categoria](image-2.png)

- Selecione a planilha Controle de Estoque que você criou

![selecao da planilha criada para o uso do aplicativo anteriormente](image-3.png)
![demonstrando a procura pela planilha e selecionando](image-4.png)

- O AppSheet vai gerar automaticamente uma interface inicial com base nas aba Estoque

![tela inicial apos a selecao da planilha, interface inicial com base na aba de estoque](image-5.png)

- Perceba que todas as colunas da planilha viraram campos que vamos utilizar, conforme a imagem.

![visualizacao das colunas criadas na planilha](image-6.png)

## 4. Personalizando e continuando o App

A. Adicionar as tabelas
    - Vá em Data > add new Data > add Table > Adicione Compras e depois Vendas

![Adicionando a tabela de movimentacao](image-7.png)

- Feito isso, sua visão de "data", deve se parecer com o da imagem abaixo
    
    ![alt text](image-15.png)

---


### B. Ajustando o drive
- Vá em Menu > Info > Properties > App properties > Role ate o final da pagina localizando a informação de "Default app folder"

    ![alt text]![alt text](image-16.png)

- Mova a planilha que você criou para esse diretorio, após localizar a pasta no seu drive

---

### C. Configuração das tabelas
- Vá em Data > Columns > Selecione a opção da tabela Estoque, por onde vamos iniciar, sua visão deve ser algo parecido com a imagem abaixo:

    ![alt text](image-18.png)

        - Atenção, as colunas Related Compras e Related Vendas, não precisam ser criadas manualmente.
        - As colunas ComprasRealizadas, VendasRealizadas e DisponibilidadeItem, devem ser criadas manualmente, utilizando o Add Virtual Column

    - Formula utilizada na coluna ComprasRealizadas = SUM(SELECT(Compra[Quantidade], [Produto] = [_THISROW].[IdEstoque]))
    - Formula utilizada na coluna VendasRealizadas = SUM(SELECT(Vendas[Quantidade], [Produto] = [_THISROW].[IdEstoque]))
    - Formula utilizada na coluna DisponibilidadeItem = [ComprasRealizadas] - [VendasRealizadas]

    - Display name utilizado na coluna Related Compras = 'Compras relacionadas'
    - Display name utilizado na coluna Related Vendas = 'Vendas Relacionadas'
    - Display name utilizado na coluna ComprasRealizadas =  'Quantidade Comprada'
    - Display name utilizado na coluna VendasRealizadas = 'Quantidade Vendida'
    - Display name utilizado na coluna DisponibilidadeItem = 'Disponibilidade do item'

            - Atenção na coluna Foto, clique no lapis, localizado ao lado direito da coluna.
            - Identifique Type Details > Image/File folder Path > 'ProdutosImg'

        ![alt text](image-22.png)


- Vamos realizar um processo parecido para a tabela Vendas

![alt text](image-19.png)    

    - Atenção ao selecionar Ref na coluna Produto siga os passos
    - Clique no lapis, localizado ao lado direito da coluna Produto
    - Identifique Type Details > Source Table > Estoque

     - Atenção, na coluna Quantidade, clique no lapis, localizado ao lado direito da coluna.
            - Type Details >
            - Show thousands separator: Ativado
            - Display mode: Label
            - Minimum Value: 1
    
![alt text](image-23.png)


![alt text](image-20.png)

- Vamos realizar o mesmo processo para a tabela Compras

![alt text](image-21.png)

    - Atenção, repita o mesmo processo de edição na coluna quantidade, feitas na tabela de Vendas
---

### D. Adicionando o primeiro produto
- Utilize a visualização lateral para cadastrar o produto

    ![alt text](image-13.png)
    
         - Atenção, após adicionar o produto, verifique no seu drive se foi criada a pasta chamada *ProdutosImg*
    
    ![alt text](image-24.png)

---  
### E. Criando a visualização das telas

 - Vá em UX > Views > New Views

  #### Configuração da tabela Compras

  ![alt text](image-25.png)

  ![alt text](image-26.png)

  #### Configuração da tabela Estoque

![alt text](image-27.png)

![alt text](image-28.png)

#### Configuração da tabela Vendas
![alt text](image-29.png)

![alt text](image-30.png)

---
### F. Compartilhando seu app

![alt text](image-31.png)

### Visualização do app no browser

![alt text](image-32.png)

### Visualização do app no mobile

![alt text](image-33.png)


    




