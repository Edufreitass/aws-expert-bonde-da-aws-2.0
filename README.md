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

---

# Day 04

# Identity and Access Management (IAM)

Security, Identity & Compliance

- O que é o AWS Identity and Access Management (IAM)?
  - O IAM fornece controle de acesso minucioso em toda a AWS. Com o IAM, é possível controlar o acesso a serviços e recursos sob condições específicas. Use as políticas do IAM, para gerenciar permissões para seu quadro de funcionários e sistemas para garantir permissões com privilégio mínimo. O IAM é oferecido sem cobranças adicionais. 

- Como o IAM funciona e o que posso fazer com ele?
  - O IAM fornece autenticação e autorização para produtos da AWS. Um serviço avalia se a solicitação da AWS será permitida ou negada. O acesso é negado por padrão e é permitido somente quando uma política concede acesso explícito. É possível anexar políticas a funções e a recursos para controlar o acesso na AWS.

- O que são permissões com privilégio mínimo?
  - Ao definir permissões com políticas do IAM, conceda apenas as permissões necessárias para executar uma tarefa. Essa prática se chama  conceder privilégio mínimo. Você aplica permissões de privilégio mínimo no IAM definindo as ações que podem ser executadas em recursos específicos mediante condições específicas.

- Como começar a usar o IAM?
  - Comece a usar o IAM para gerenciar permissões para serviços e recursos da AWS criando uma função do IAM e concedendo permissões a ela. Para usuários do quadro de funcionários, crie uma função que possa ser assumida pelo provedor de identidade. Para sistemas, crie uma função que possa ser assumida pelo serviço que você está usando, como o Amazon EC2 ou o AWS Lambda. Após criar uma função, anexe uma política à função para conceder permissões que atendam às suas necessidades. No início, talvez você não conheça as permissões específicas necessárias, então pode começar com permissões mais abrangentes. As políticas gerenciadas pela AWS fornecem permissões para ajudar você a dar os primeiros passos e estão disponíveis em todas as contas da AWS. Depois, reduza as permissões definindo políticas gerenciadas pelo cliente específicas para seus casos de uso. Você pode criar e gerenciar políticas e funções pelo console do IAM, pelas APIs da AWS ou pela AWS CLI. 

- O que são as funções (roles) do IAM e como elas funcionam?
  - As funções do AWS Identity and Access Management (IAM) fornecem um modo de acessar a AWS com base em credenciais de segurança temporárias. Cada função tem um conjunto de permissões para fazer solicitações de produtos da AWS, e uma função não está associada a um usuário ou grupo específico. Em vez disso, entidades confiáveis, como provedores de identidade ou produtos da AWS, assumem funções. 

- Por que usar as funções (roles) do IAM?
  - Você deve usar funções do IAM para conceder acesso a suas contas da AWS com base em credenciais de curto prazo, uma prática recomendada de segurança. As identidades autorizadas, que podem ser produtos da AWS ou usuários de seu provedor de identidade, podem assumir funções para fazer solicitações à AWS. Para conceder permissões a uma função, anexe uma política do IAM a ela.

- O que são usuários do IAM? Devo continuar usando-os?
  - Os usuários do IAM são identidades com credenciais de longo prazo. Talvez você esteja usando usuários do IAM para usuários de quadro de funcionários. Nesse caso, a AWS recomenda usar um provedor de identidade e federá-lo na AWS assumindo funções. Também é possível usar funções para conceder acesso entre contas a serviços e recursos, como funções do AWS Lambda. Em alguns cenários, você pode exigir que usuários do IAM com chaves de acesso com credenciais de longo prazo tenham acesso a sua conta da AWS. Para esses cenários, a AWS recomenda usar as últimas informações de acesso ao IAM usadas para alternar as credenciais frequentemente e remover as credenciais que não estão em uso.

- O que são políticas (policies) do IAM?
  - As políticas do IAM definem permissões para as entidades às quais são anexadas. Por exemplo, para conceder acesso a uma função do IAM, anexe uma política à função. As permissões definidas na política determinam se as solicitações serão permitidas ou negadas. Também é possível anexar políticas a alguns recursos, como buckets do Simple Storage Service (Amazon S3), para conceder acesso direto entre contas. E você pode anexar políticas a uma organização ou unidade organizacional da AWS para restringir o acesso a várias contas. A AWS avalia essas políticas quando uma função do IAM faz uma solicitação. 
