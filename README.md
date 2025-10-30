# DIO---AWS
Projeto prático desenvolvido no curso AWS Cloud (DIO). Implementação de uma arquitetura base na AWS utilizando serviços como EC2, S3 e EBS, focada em IaaS e otimização de custos.

Neste repositório, vocês encontrarão uma etapa importante em minha jornada durante o curso de AWS Cloud, pela DIO. O foco dessa primeira etapa, é sair da teoria, e poder consolidar o gerenciamente de instâncias Amazon EC2. 
Basicamente, trata-se de uma documentação, onde a principal entrega não é o código, mas o conhecimento estruturado. 

O que anotei e documentei:
- O ciclo completo de instâncias, AMIs e tipos de instâncias.
- O papel do Amazon EBS e como volumes são anexados e gerenciados.
- O primeiro contato com a AWS Cloud
- Entre outros.

Como dito, este é o meu primeiro contato com a plataforma, e com a utilização de nuvens na TI. 
Aqui, você encontrará alguns pontos que achei importante ressaltar sobre este curso. 


<img width="1135" height="531" alt="image" src="https://github.com/user-attachments/assets/aaf2715e-0e28-46f8-a391-567043be5ab0" />


<img width="1512" height="988" alt="image" src="https://github.com/user-attachments/assets/4c0e9c54-cfe6-4c74-84c6-38a7c8972857" />



Abaixo, você pode conferir o desenho de Arquitetura desenvolvido para este projeto:


<img width="798" height="709" alt="image" src="https://github.com/user-attachments/assets/138046d0-499c-4aff-9273-e3745c18c2a2" />

Fluxo de Dados e Interações
Gerenciamento Central: A instância EC2 é o ponto focal que se conecta e gerencia tanto os volumes de armazenamento (EBS) quanto o banco de dados gerenciado (RDS).

Transferência de Dados: O Admin e o SYSTEM interagem com o ambiente, sendo que o Admin possui a capacidade de "Enviar Arquivo" para o ambiente.

Armazenamento e Aplicação: A aplicação em execução no EC2 usa o RDS para dados transacionais e os volumes EBS (D e E) para arquivos do sistema ou dados secundários de bloco.

Este é apenas um exemplo do entendido até o momento. 
É uma arquitetura comum para hospedar uma aplicação que exige computação dedicada (EC2) e um banco de dados relacional (RDS), com um administrador responsável pela gestão e injeção de arquivos.


Até a próxima!
