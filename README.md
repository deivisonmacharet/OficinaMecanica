Descrição do Projeto

O projeto tem como objetivo desenvolver um sistema de controle e gerenciamento de ordens de serviço (OS) para uma oficina mecânica. O sistema permitirá o cadastro de clientes, seus veículos, as ordens de serviço emitidas, os serviços prestados, os mecânicos responsáveis e os produtos utilizados. A partir das OSs, será possível calcular o custo total do serviço, considerando a mão de obra e as peças utilizadas.

Entidades e Relacionamentos

Cliente
id_cliente
nome
telefone
email
endereco

Veículo
id_veiculo (PK)
placa (Unique)
modelo
marca
ano
id_cliente (FK)

Ordem de Serviço
id_os (PK)
data_emissao
status
valor_total
data_conclusao
id_veiculo (FK)

Mecânicos
id_mecanico (PK)
nome
endereco
especialidade

Equipe_Mecanicos
id_equipe (PK)
id_os (FK)
id_mecanico (FK)

Serviço
id_servico (PK)
descricao
valor_mao_obra

Serviço_Executado
id_servico_executado (PK)
id_os (FK)
id_servico (FK)
id_mecanico (FK\0


Regras de Negócio

* Cada veículo pertence a apenas um cliente, mas um cliente pode ter vários veículos.
* Cada OS está vinculada a apenas um veículo.
* Cada OS possui uma equipe de mecânicos responsáveis.
* Cada OS pode conter vários serviços executados e produtos utilizados.
* O custo total da OS é calculado somando o valor da mão de obra dos serviços prestados e o valor das peças utilizadas.
* O status da OS define o andamento do serviço.
