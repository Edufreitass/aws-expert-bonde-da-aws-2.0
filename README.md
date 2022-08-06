# LINUXtips - AWS Expert #BondeDaAWS 2.0

![image](https://user-images.githubusercontent.com/56324728/182739233-497e12f4-7b63-4ba8-855b-2d04512aaa10.png)

# Day 01

# What is Cloud?

A computação em nuvem é a entrega de recursos de TI sob demanda por meio da Internet com definição de preço de pagamento conforme o uso. Em vez de comprar, ter e manter datacenters e servidores físicos, você pode acessar serviços de tecnologia, como capacidade computacional, armazenamento e bancos de dados, conforme a necessidade, usando um provedor de nuvem como a Amazon Web Services (AWS).

# Characteristics and Advantages

- Agility
- Maintenance
- Reliability
- Security
- Performance
- Scalability
- Cost and Elasticity
- Extra:
  - NIST (The National Institute of Standards and Technology)
    - On demand self-service
    - Broad network access
    - Resource pooling
    - Rapid elasticity
    - Measured service

# Service models

- **IaaS (Infrastructure as a Service)**
- **PasS (Platform as a Service)**
- **FaaS (Function as a Service)**
  - SaaS (Software as a Service)
  - CaaS (Container as a Service)
  - BaaS (Backend as a Service)
  - Haas (Hardware as a Service)

# Deployment models

- Private Cloud
- Public Cloud
- Hybrid Cloud
- *Multicloud
- Community

---

# Day 02

# Foundation - Intro

![image](https://user-images.githubusercontent.com/56324728/182744471-13214fb4-54ea-4334-91ac-7127623e870a.png)

- Root Accounts
  - O objetivo da Root Account é gerenciar outras contas e dados de billing.
  - Boas práticas:
    - NÃO utilizar a Root Account para realizar deploys de serviços na AWS.
    - Você pode usar Organizational Unit (OU) para agrupar contas e administrá-las como uma unidade única. Isso simplifica bastante o gerenciamento de suas contas.

- AWS Accounts
  - Na camada de Accounts é o lugar ideal para criar os seus serviços(EC2, Lambda, etc..)

- Creating Account
  - My Security Credentials
    - A primeira ação a ser feita após a criação da conta, é a realizar a configuração do MFA (Multi-factor Authentication)

# Quiz

1. Em uma Organization com 10 AWS Accounts, quantas Root Accounts existem?
  ```
  10
  ```
2. Qual a finalidade de uma OU na AWS?
  ```
  Organizar visualmente AWS Accounts e nas regras de segurança dos serviços
  ```
3. Uma Service Control Policy, pode ser aplicada em quais objetos?
  ```
  OU e Accounts
  ```
4. O que melhor defini os custos de criação de AWS Accounts?
  ```
  Não existe custo
  ```
5. Quantas horas por mês pode ser utilizado o serviço de maquinas virtuais da AWS de forma gratuita?
  ```
  750 horas
  ```
6. Um cliente, quer migrar seu data center para a nuvem e continuar usando os serviços de VMs que hoje ele tem local. Qual modelo de Cloud é mais apropriado para ele?
  ```
  IaaS - Infrastructure as a Service
  ```
7. Qual dessas afirmações esta correta
  ```
  Cloud Computing ajuda na adoção de DevOps
  ```
8. Qual a diferença entre Master Account de Root Account?
  ```
  Master Account é a primeira conta criada na AWS e Root Account é o usuário dono de uma AWS Account
  ```

# Exercício:

```
Quando terminar de responder as perguntas acima, faça este exercício.

Scenario 1: Crie uma outra conta na AWS, acessando sua conta principal no menu My Organization, através da segunda opção Create account.
Scenario 2: Agora, crie uma outra conta usando a opção Invite account. Para isso, você precisar criar essa conta antes.
No total do dia, você precisa ter 3 contas criadas na AWS, na seguinte estrutura:

Organizaçõa das contas:

Master Account/Payer Account
    1 OU: Dev
      Dev Account
    1 OU: Prod
      Prod Account
      
Na conta de Dev, os usuarios não devem conseguir criar RDS
Na conta de Prod, os usuarios não devem conseguir criar S3

Simule o uso dessas Service Control Policy (SCP) em cada conta, usando outros browsers para poder logar
em multiplas contas ao mesmotempo.
Ex.: Chrome para logar na Master Account, Firefox para logar na conta Dev com o Root(email da conta) e 
Modo incognito do firefox ou do Chrome para logar na conta de Prod com o Root(email da conta).

Obs: Use SCP para definir essas regra, e attach em cada conta sua respectiva SCP.
Execute o exercicio, grave um video da sua tela e envie o resultado no grupo do Telegram, me marque lá(Mateus Prado)
Imagina que você quer que alguem pegue esse material e consiga fazer sozinho, como se você estivesse fazendo um tutorial, how-to para a comunidade! Como você gostaria que fosse esse material? Pense como se fosse você procurando isso no Google :)

Troque informações no grupo do Telegram, tire dúvidas, compartilhe idéias com os colegas do grupo.

Boa sorte

Mateus
```

---

# Day 03

# AWS Well-Architected

O AWS Well-Architected Framework descreve os principais conceitos, princípios de projeto e práticas recomendadas para projetar e executar workloads na nuvem. Ao responder algumas perguntas fundamentais, você aprende o quanto sua arquitetura se alinha com as práticas recomendadas da nuvem e recebe orientações para fazer melhorias.

- Pilars
- Design Principles
- Questions

- Why apply the AWS Well-Architected Framework?
  - Speed
  - Mitigate Risks
  - Make informed decisions
  - Use AWS best practices

- Cycles:
  - Learn
  - Measure
  - Improve

```
Se você já usa AWS, escolha uma aplicação, um serviço específico e tente rodar o Well-Architected nele. Não publique os resultados, use isso dentro da empresa.
Leia cada paper do Well-Architected que está na doc(veja em Links) e entenda mais degtalhes de cada Pilar do framework

Execute na sua conta pessoal da AWS o Well-Architected, criando um workload inicial para medir a qualidade de cada pilar na sua conta inicial.
Vá durante o treinamento, criando milestones, e vendo a evolução da sua conta.
No final do treinamento, vamos rever cada pilar juntos.
```
