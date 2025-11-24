# 💰 Proposta Orçamentária - Nextcloud AWS

Documentação completa de custos e análise financeira da infraestrutura Nextcloud hospedada na AWS.

## 📋 Visão Geral

Este repositório contém a proposta orçamentária detalhada para a infraestrutura Nextcloud Version 2, incluindo análise de custos, comparativos com a infraestrutura antiga, e oportunidades de otimização.

## 🎯 Informações do Projeto

- **Cliente:** Henrylle Maia
- **Projeto:** Nextcloud Version 2
- **Região AWS:** us-east-1 (Norte da Virgínia)
- **Domínio:** [nextcloud.cloud.flog.br](https://nextcloud.cloud.flog.br/login)
- **Repositório:** [github.com/nextcloudv2](https://github.com/nextcloudv2)
- **Data de Entrega:** 26 de Novembro de 2025

## 💵 Resumo de Custos

### Custo Atual (Sem Otimizações)
- **Mensal:** $263.31 (R$ 1.448,21)
- **Anual:** $3.159,72 (R$ 17.378,46)

### Custo Otimizado (Com Reserved Instances e Savings Plans)
- **Mensal:** $172.80 (R$ 950,40)
- **Anual:** $2.073,60 (R$ 11.404,80)

### Economia vs Infraestrutura Antiga
- **Economia Anual:** $5.606,40 (R$ 30.835,20)
- **Redução:** 73.0% nos custos anuais

## 📊 Distribuição de Custos

| Categoria | Custo Mensal | % do Total |
|-----------|--------------|------------|
| EC2 (Computação) | $126.27 | 47.9% |
| RDS (Banco de Dados) | $60.27 | 22.9% |
| Rede e DNS | $42.75 | 16.2% |
| ALB (Load Balancer) | $16.83 | 6.4% |
| WAF | $10.60 | 4.0% |
| Monitoramento | $3.80 | 1.4% |
| CI/CD | $2.00 | 0.8% |
| Segurança | $0.51 | 0.2% |
| EFS (Storage) | $0.28 | 0.1% |

## 🏗️ Infraestrutura

### Recursos Principais
- ✅ **2x EC2 t3.large** - Alta Disponibilidade em Multi-AZ
- ✅ **Aurora PostgreSQL** (db.t4g.medium) - Banco gerenciado
- ✅ **Application Load Balancer** - Distribuição de carga com SSL/TLS
- ✅ **EFS** - Storage persistente (~931 MB)
- ✅ **Route53** - Gerenciamento DNS
- ✅ **WAF** - Proteção contra ataques
- ✅ **CloudWatch** - Monitoramento 24/7

### Tecnologias Utilizadas
- **Terraform** - Infrastructure as Code
- **CodePipeline + CodeBuild** - CI/CD automatizado
- **ECR** - Container registry
- **ECS Fargate** - Orquestração de containers
- **Secrets Manager** - Gerenciamento de credenciais
- **VPC Peering** - Replicação entre regiões

## 🚀 Melhorias vs Infraestrutura Antiga

| Aspecto | Antiga (2020-2025) | Nova (2025) |
|---------|-------------------|-------------|
| **Custo Mensal** | $640.00 | $263.31 (-58.9%) |
| **Disponibilidade** | Single AZ | Multi-AZ (99.99%) |
| **Backup** | Manual | Automático |
| **Escalabilidade** | Não | Auto Scaling |
| **Segurança** | SSH direto | Session Manager + WAF |
| **CI/CD** | Manual | Automatizado |
| **IaC** | Não | Terraform |

## 💡 Oportunidades de Otimização

| Otimização | Economia Mensal | Economia Anual |
|------------|-----------------|----------------|
| Reserved Instances (EC2) | -$40.28 | -$483.36 |
| Reserved Instances (RDS) | -$18.08 | -$216.96 |
| Savings Plans | -$32.00 | -$384.00 |
| EFS Infrequent Access | -$0.15 | -$1.80 |
| **Total** | **-$90.51** | **-$1.086,12** |

## 📁 Arquivos

- **`PROPOSTA_ORCAMENTARIA_NEXTCLOUD.html`** - Proposta completa em HTML
- **`DOCUMENTACAO_COMPLETA(1).html`** - Documentação técnica detalhada
- **`ANALISE_PAYBACK_ROI.html`** - Análise de retorno de investimento
- **`Screenshot from 2025-11-04 15-23-12.png`** - Diagrama de arquitetura

## 🔧 Processo de Migração

A migração foi realizada utilizando:

1. **Backup e Restore** - PostgreSQL da EC2 para Aurora RDS
2. **EFS Replication** - VPC Peering entre São Paulo e Virgínia
3. **Aurora Global Database** - Replicação com latência <1s
4. **Containerização** - Docker + ECR + ECS Fargate
5. **CI/CD Pipeline** - Automação completa de deploys
6. **WAF** - Proteção contra ataques
7. **Terraform** - Infraestrutura versionada em Git

**Downtime:** Apenas 15 minutos durante o cutover final

## 📞 Contato

Para mais informações sobre a proposta orçamentária, entre em contato com a equipe do projeto.

---

**Cotação:** US$ 1,00 = R$ 5,50  
**Última Atualização:** 26 de Novembro de 2025
