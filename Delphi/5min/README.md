# Aplicação Drag-and-Drop com Banco de Dados

- **VCL Forms Application**
  - `TDBNavigator` : Botões para navegação CRUD
    - Visible Buttons
  - `TDBGrid` : Tabela de exibição dos dados
    - `DataSouce`

- **Data Module** (com FireDac)
  - `TFDConnection`
    - Login Prompt: False
    - Conneted: True
    - Driver ID: MySQL
    - User_Name
    - Password
    - Port
    - Database
  - `TFDQuery`
    - Query Editor: SELECT * FROM tb_pessoas;
    - Filds Editor/ Add Fields / (drag-drop)
    - Active: True
  - `TFDGuixWaitCursor`
    - Ajuste funcional
  - `TDataSource`
    - DataSet: `FDQuery`

 
