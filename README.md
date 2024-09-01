# Kong API Gateway com Konga - Implantação Local e em Kubernetes

Este repositório fornece uma configuração completa para implantar o Kong API Gateway com a interface gráfica Konga, tanto em um ambiente local de desenvolvimento usando Docker Compose quanto em um cluster Kubernetes usando Helm.

## Estrutura do Repositório

- **docker-compose.yml**: Define os serviços (Kong, Konga, banco de dados) para execução local com Docker Compose.
- **values.yaml**: Contém as configurações para implantação no Kubernetes com Helm.
- **charts/kong/**: Diretório com os arquivos do Helm Chart para o Kong.

## Como Usar

### Localmente (Docker Compose)
1. Certifique-se de ter o Docker e o Docker Compose instalados.
2. Clone este repositório.
3. Na raiz do projeto, execute `docker-compose up -d`.
4. Acesse o Konga em [http://localhost:1337](http://localhost:1337) e o Kong Admin API em [http://localhost:8001](http://localhost:8001).

### Em Kubernetes (Helm)
1. Certifique-se de ter o Helm instalado e configurado para acessar seu cluster Kubernetes.
2. Clone este repositório.
3. Adicione o repositório do Kong ao Helm:  
   ```bash
   helm repo add kong https://charts.konghq.com
4. Atualize os repositórios:
    ```bash
    helm repo update
5. Instale o Kong
  ```bash
  helm install kong-gateway-management kong/kong --values values.yaml
6. Acesse o Konga e o Kong Admin API através dos serviços expostos no seu cluster.

## Configurações

- Adapte as portas, senhas e outros detalhes nos arquivos `docker-compose.yml` e `values.yaml` conforme seu ambiente.
- Para persistir dados do banco de dados localmente, configure volumes no `docker-compose.yml`.
- Configure o Ingress no Kubernetes para expor o Kong e o Konga externamente, se necessário.

## Observações

- Este é um exemplo básico. Adapte-o às suas necessidades e explore as opções de configuração do Kong, Konga, Docker Compose e Helm.
- Mantenha o Kong e o Konga atualizados para garantir compatibilidade e segurança.
- Utilize práticas de segurança adequadas, como autenticação e controle de acesso, especialmente em ambientes de produção.

## Contribuições

Contribuições são bem-vindas! Sinta-se à vontade para abrir issues ou pull requests.


