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
    - Utilize o AWS Organizations para ajudar a gerenciar e controlar seu ambiente de maneira centralizada à medida que os negócios e seus recursos da AWS expandem.

- AWS Accounts
  - Na camada de Accounts é o lugar ideal para criar os seus serviços(EC2, Lambda, etc..)
