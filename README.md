# RESILIADATA - Sistema de Gerenciamento de Parceiros e Tecnologias
![image](https://github.com/Delson2000/Projeto-Individual-M2-Cnseg/assets/112819612/a04b5199-9bb2-4158-92e2-d675e7827a53)
https://lucid.app/publicSegments/view/645790e4-1926-43e7-9969-27e98389bcc1/image.png

O RESILIADATA é um sistema de banco de dados desenvolvido para auxiliar na gestão de informações sobre empresas parceiras, tecnologias utilizadas e colaboradores associados a essas empresas. Este README fornece uma visão geral do esquema do banco de dados e como as entidades estão relacionadas.

## Esquema do Banco de Dados

O banco de dados RESILIADATA consiste em quatro principais entidades:

1. **Empresa Parceira**: Armazena informações sobre empresas que são parceiras.
   
   - Campos:
     - ID (Chave Primária)
     - Nome
     - Endereço
     - Contato

2. **Tecnologia**: Armazena informações sobre diferentes tecnologias e suas áreas de aplicação.
   
   - Campos:
     - ID (Chave Primária)
     - Nome
     - Área

3. **Colaborador**: Armazena informações sobre os colaboradores das empresas parceiras.
   
   - Campos:
     - ID (Chave Primária)
     - Nome
     - Cargo
     - EmpresaParceiraID (Chave Estrangeira referenciando a tabela Empresa Parceira)

4. **Projeto**: Armazena informações sobre os projetos associados às empresas parceiras.
   
   - Campos:
     - ID (Chave Primária)
     - Nome
     - Descrição
     - EmpresaParceiraID (Chave Estrangeira referenciando a tabela Empresa Parceira)

## Relacionamentos

- **Empresa Parceira e Tecnologia**: Relacionamento muitos para muitos (N:M).
   - Uma empresa parceira pode utilizar várias tecnologias e uma tecnologia pode ser utilizada por várias empresas parceiras.

- **Empresa Parceira e Colaborador**: Relacionamento um para muitos (1:N).
   - Um colaborador trabalha para apenas uma empresa parceira, mas uma empresa pode ter vários colaboradores.

- **Empresa Parceira e Projeto**: Relacionamento um para muitos (1:N).
   - Um projeto pertence a uma única empresa parceira, mas uma empresa pode ter vários projetos.

- **Projeto e Tecnologia**: Relacionamento muitos para muitos (N:M).
   - Um projeto pode utilizar várias tecnologias e uma tecnologia pode ser utilizada por vários projetos.
    
- **Colaborador e Projeto**: Relacionamento muitos para muitos (N:M)
   - Um colaborador pode estar associado a múltiplos projetos e um projeto pode ter múltiplos colaboradores.


## Exemplo de Uso

Aqui está um exemplo de como as tabelas podem ser populadas com dados:

```sql
-- Inserindo dados de empresas parceiras
INSERT INTO resilia.EmpresaParceira (ID, Nome, Endereco, Contato) VALUES
(1, 'Empresa A', 'Endereço A', 'Contato A'),
(2, 'Empresa B', 'Endereço B', 'Contato B');

-- Inserindo dados de tecnologias
INSERT INTO resilia.Tecnologia (ID, Nome, Area) VALUES
(1, 'Java', 'Webdev'),
(2, 'Python', 'Data');

-- Inserindo dados de colaboradores
INSERT INTO resilia.Colaborador (ID, Nome, Cargo, EmpresaParceiraID) VALUES
(1, 'João', 'Desenvolvedor', 1),
(2, 'Maria', 'Analista de Dados', 2);

-- Inserindo dados de projetos
INSERT INTO resilia.Projeto (ID, Nome, Descricao, EmpresaParceiraID) VALUES
(1, 'Projeto X', 'Descrição do Projeto X', 1),
(2, 'Projeto Y', 'Descrição do Projeto Y', 2);
```

Este é apenas um exemplo básico de como inserir dados no banco de dados RESILIADATA.

---





