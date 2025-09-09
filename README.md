# 🚗 Sistema de Controle e Gerenciamento de Ordens de Serviço - Oficina Mecânica

Este projeto apresenta a modelagem conceitual de um banco de dados para um sistema de controle e gerenciamento de ordens de serviço (OS) em uma oficina mecânica. O modelo foi desenvolvido com o objetivo de atender à narrativa fornecida, garantindo a organização e rastreabilidade de todos os processos, desde a entrada do veículo até a conclusão do serviço.

🎯 **Descrição do Desafio**

O desafio consistiu em criar um esquema conceitual de banco de dados do zero, a partir de uma narrativa específica para uma oficina mecânica. O objetivo era definir todas as entidades, relacionamentos, atributos e chaves primárias/estrangeiras.

📖 **Narrativa do Projeto**

A oficina mecânica gerencia o fluxo de veículos que chegam para consertos ou revisões. Cada veículo é atribuído a uma equipe de mecânicos que, após diagnóstico, preenche uma Ordem de Serviço (OS), definindo a data de entrega. O valor total da OS é calculado com base em uma tabela de referência de mão de obra e no valor das peças utilizadas. É necessária a autorização do cliente para a execução dos serviços. Os mecânicos possuem informações como código, nome, endereço e especialidade. Uma OS inclui número, data de emissão, valor total, status e data de conclusão.

🛠️ **Ferramenta utilizada**

MySQL Workbench 8.0 (diagrama ER)

Link para download: https://www.mysql.com/products/workbench/

## 📊 Diagrama do Projeto

### Modelo Conceitual 
![Modelo Conceitual ](Imagens/modeleagem_conceitual_bd_oficina.png
)



💡 **Justificativas e Decisões de Modelagem**

- Separação de Responsabilidades: Entidades como Cliente, Veiculo, Mecanico, OrdemServico, Pecas e Servicos foram criadas para isolar responsabilidades e evitar redundância de dados.

- Gerenciamento de Equipes: A criação da entidade Equipe e seu relacionamento com Mecanico permite agrupar mecânicos e gerenciar quem está alocado em qual trabalho.

- Cálculo de Custos: A separação entre Servicos (a descrição e valor da mão de obra do serviço em si) e MaoDeObra (uma tabela de referência de custos, possivelmente mais genérica ou com diferentes tabelas baseadas em horários/complexidade) permite um controle mais preciso dos custos. 

- Tabelas de Junção (N:N): O uso de Servicos_has_OrdemServico e Pecas_has_Servicos é fundamental para modelar corretamente os relacionamentos muitos-para-muitos, garantindo que uma Ordem de Serviço possa ter vários serviços e peças, e que um serviço/peça possa ser usado em diversas Ordens de Serviço.

- Chaves Estrangeiras: Foram cuidadosamente definidas para garantir a integridade referencial entre as tabelas.



