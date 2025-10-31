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


O AWS Step Functions é um serviço de orquestração sem servidor (serverless) que permite que você crie workflows visualmente para coordenar e integrar diferentes serviços da AWS, bem como microsserviços e aplicações externas.

Ele atua como um gerenciador de estados centralizado, o que é especialmente útil para automatizar processos de negócios e de TI complexos.


Funcionalidades e Benefícios Principais:

- Orquestração de Fluxos de Trabalho: Permite criar "Máquinas de Estado" que definem uma sequência lógica (fixa ou dinâmica) de tarefas.
- Integração Nativa: Facilita a integração com mais de 220 serviços da AWS, incluindo AWS Lambda, Amazon S3, DynamoDB, Amazon EKS e muito mais, sem a necessidade de escrever código de integração complexo ponto a ponto.
- Controle de Estado: Mantém o estado centralizado do fluxo de trabalho, o que permite que o processo pause, aguarde interações humanas (como uma aprovação por e-mail) ou continue, e gerencia a transformação de dados entre as etapas.
- Tratamento de Erros: Oferece lógica embutida para tratamento de erros, novas tentativas (retries) e lógica condicional (conditional logic), tornando os fluxos de trabalho distribuídos mais robustos, confiáveis e resilientes.
- Visualização e Auditoria: Oferece uma interface gráfica de usuário (GUI) que permite visualizar o fluxo completo, monitorar cada passo em tempo real e auditar o que aconteceu (entrada e saída de cada estado).
- Tipos de Fluxo: Suporta dois tipos principais de fluxos de trabalho:
- Standard (Padrão): Ideal para fluxos de longa duração (podendo durar até um ano).
- Express: Voltado para fluxos de alta taxa e curta duração (com execuções de até 5 minutos), como ingestão de dados em tempo real.



  O AWS CloudFormation é um serviço fundamental que implementa o conceito de Infraestrutura como Código (IaC) na AWS.

O que é o AWS CloudFormation?
Definição: É um serviço que permite provisionar e gerenciar recursos da AWS (e até mesmo externos) usando arquivos de modelo declarativos escritos em YAML ou JSON.

Pilhas (Stacks): O CloudFormation interpreta o modelo (template) e provisiona todos os recursos definidos (EC2, S3, DynamoDB, etc.) em um grupo único e coeso chamado pilha (stack).

Consistência e Repetibilidade: O principal benefício é a padronização da infraestrutura. Você pode replicar a mesma arquitetura de forma rápida e confiável em diferentes regiões ou contas, eliminando erros de configuração manual (drift).


Gerenciamento: As stacks facilitam a implantação, atualização e exclusão de um grupo de recursos relacionados em uma única operação. Se um recurso falhar durante a criação, o CloudFormation reverte automaticamente a stack, garantindo a consistência do ambiente.

StackSets: Uma extensão avançada que permite implantar uma stack em múltiplas Contas da AWS e Regiões simultaneamente.

Stacks de Firewall no CloudFormation
O CloudFormation é amplamente utilizado para gerenciar e padronizar recursos de segurança e firewall:

Infraestrutura de Segurança como Código: É possível definir recursos de rede e segurança, como Security Groups, Network ACLs e até mesmo serviços avançados de firewall, diretamente nos templates do CloudFormation.


AWS Firewall Manager: O AWS Firewall Manager (um serviço de gerenciamento de segurança) possui suporte nativo ao CloudFormation. Isso permite que os clientes gerenciem e apliquem centralmente políticas de firewall em toda a organização (incluindo AWS WAF, AWS Shield Advanced e Security Groups) usando um único template.

AWS WAF: Modelos do CloudFormation são usados para provisionar recursos do AWS WAF (Web Application Firewall), incluindo a criação de Web ACLs e a configuração de regras contra ataques comuns.

AWS Network Firewall: Amostras de templates do CloudFormation estão disponíveis para provisionar o AWS Network Firewall, facilitando a inspeção e filtragem do tráfego VPC em diferentes arquiteturas (distribuída ou centralizada).

O uso de CloudFormation para firewalls garante que as regras de segurança sejam consistentes e aplicadas uniformemente em toda a infraestrutura.

O AWS CloudFormation utiliza templates (modelos) para definir e provisionar recursos de infraestrutura como código (IaC). Esses templates são arquivos de texto que descrevem os recursos que você deseja criar na AWS, sendo essencialmente utilizados em dois formatos principais: YAML e JSON.

<img width="761" height="167" alt="image" src="https://github.com/user-attachments/assets/b5f0e4b4-88ea-49c5-a3c1-3ef3abb153c9" />


Independentemente do formato (YAML ou JSON), o template do CloudFormation segue uma estrutura lógica que inclui:

AWSTemplateFormatVersion: Define a versão do formato do template.

Description: Define a descrição do template (útil para detalhar o que está sendo criado).

Resources: É a seção principal onde você define todos os recursos da AWS a serem provisionados (como EC2, S3, tabelas DynamoDB, etc.).

Parameters: Permite criar templates dinâmicos (reutilizáveis) onde o usuário fornece valores de entrada na hora da execução (ex: tipo de instância EC2 ou nome do bucket S3).

Outputs: Define os valores que serão retornados após a criação da stack (ex: o endereço DNS de um Load Balancer).

O CloudFormation interpreta esse template e provisiona os recursos em um grupo chamado Stack.


No CloudFormation, a infraestrutura é provisionada através do conceito de Stacks (Pilhas).

Template (Modelo): Você começa definindo o estado desejado dos seus recursos AWS (como instâncias EC2, sub-redes, etc.) em um arquivo declarativo chamado template, escrito em YAML ou JSON.

Stack: O CloudFormation interpreta esse template e provisiona todos os recursos nele descritos como uma única unidade. Essa unidade de recursos relacionados é chamada de Stack.

Rollback Automático: Se ocorrer uma falha durante o processo de criação ou atualização da stack, o CloudFormation possui um recurso nativo de rollback, revertendo automaticamente todos os recursos criados ao último estado funcional conhecido, o que ajuda a prevenir downtime e simplifica a solução de problemas.

Gerenciamento do Estado: O gerenciamento do estado da stack é feito automaticamente pela AWS.


O AWS CloudFormation e o Terraform são as duas ferramentas mais proeminentes para Infraestrutura como Código (IaC), embora tenham filosofias e escopos de atuação distintos.

1. Criação de Stacks (Pilhas) no AWS CloudFormation
No CloudFormation, a infraestrutura é provisionada através do conceito de Stacks (Pilhas).

Template (Modelo): Você começa definindo o estado desejado dos seus recursos AWS (como instâncias EC2, sub-redes, etc.) em um arquivo declarativo chamado template, escrito em YAML ou JSON.

Stack: O CloudFormation interpreta esse template e provisiona todos os recursos nele descritos como uma única unidade. Essa unidade de recursos relacionados é chamada de Stack.

Rollback Automático: Se ocorrer uma falha durante o processo de criação ou atualização da stack, o CloudFormation possui um recurso nativo de rollback, revertendo automaticamente todos os recursos criados ao último estado funcional conhecido, o que ajuda a prevenir downtime e simplifica a solução de problemas.

Gerenciamento do Estado: O gerenciamento do estado da stack é feito automaticamente pela AWS.


A tabela abaixo resume as principais diferenças entre as ferramentas:


<img width="485" height="490" alt="image" src="https://github.com/user-attachments/assets/45890566-9466-4a83-a6c0-9aa38c0a062c" />

Em resumo, se a organização opera exclusivamente na AWS, o CloudFormation oferece uma experiência mais integrada e gerenciada. Se a estratégia envolve múltiplas nuvens ou serviços externos, o Terraform é geralmente a escolha mais flexível e universal.

Até a próxima!
