# JTable


 - `JTable(Object[][] rowData, Object[] columnNames)`
   - Constrói um novo JTable com o array de dados e os nomes de colunas indicados

## TableModel

~~~Java
 TableModel modeloTabela = new MyTableModel();
 JTable tabela = new JTable(modeloTabela);
~~~      

## JScrollPane

- Dados
~~~
String[] colunas = new String[]{"Nome","Idade","Sexo"};
  
String[][] dados = new String[][]{
 
    {"Rodrigo","28","Masculino"},
    {"Maria","30","Feminino"}

};
~~~

- Exemplo 1
~~~
  JTable tabela = new JTable(dados,colunas);
  
  JScrollPane scroll = new JScrollPane();
  scroll.setViewportView(tabela);
  this.add(scroll);
~~~

- Exemplo 2
~~~
  JTable tabela = new JTable();

  DefaultTableModel model = new DefaultTableModel(dados , colunas );
  tabela.setModel(model);
  
  JScrollPane scroll = new JScrollPane();
  scroll.setViewportView(tabela);
  
  this.add(scroll);
~~~
