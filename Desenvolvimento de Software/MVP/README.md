# Arquitetura MVP

-  concentra-se em melhorar a lógica de apresentação.
- é uma evoluçao do MVC, que corresponde a um total desacoplamento.
- há uma relação um-para-um entre as camadas. Ha uma referência do View para o Presenter, mas não o oposto.
- é possivel vincular dados da View com o Model através de _data binding_. Isso ocorre na variação _Supervising Controller_, em oposição à variação _Passive View_ onde a View essencialmente só possui o desenho da UI.
- a View pode conter código para manipular a UI (User Interface).
- Windows Forms é um exemplo de MVP

----- 

- `Model` : conjunto de classes que descreve a lógica de negócios e os dados. Define regras de negócio para os dados e como os dados podem ser alterados.
- `View` : faz interação com o usuário.
  - `iView` : interface da View onde o Presenter implementará suas declarações.
- `Presenter` : Obtem as entradas da View, processa os dados com ajuda do Model e passa os resultados de volta para View (apos o processamento ser concluído).
