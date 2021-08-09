# Arquitetura MVP

Model View Presenter

- é uma evoluçao do MVC, que corresponde a um total desacoplamento.
- há uma relação um-para-um entre as camadas. Ha uma referência do View para o Presenter, mas não o oposto.
- é possivel vincular dados da View com o Model através de _data binding_. Isso ocorre na variação _Supervising Controller_, em oposição à variação _Passive View_ onde a View essencialmente só possui o desenho da UI.
- a View pode conter código para manipular a UI (User Interface).
- Windows Forms é um exemplo de MVP
