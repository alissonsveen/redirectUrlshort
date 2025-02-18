#  🔗 **Redirecionador de URL em Java** 🚀

Este projeto é um **redirecionador de URL** simples desenvolvido em Java, utilizando AWS Lambda para gerenciamento e S3 para armazenamento. Ele é responsável por encurtar URLs e realizar redirecionamentos baseados em entradas fornecidas.

## 💻 **Tecnologias Utilizadas**:

- **AWS Lambda** 📦
- **Jackson** (para manipulação de JSON) 🔧
- **Amazon S3** (armazenamento de URLs) 🗃️
- **AWS SDK** (para integração com S3) ☁️

## 🧩 **Como Funciona**:

O funcionamento do redirecionador de URL é bem simples e pode ser dividido em quatro etapas principais:

### 1. **Recebimento da Requisição:**
O usuário faz uma solicitação via API para encurtar uma URL. Essa solicitação pode ser feita por HTTP ou outras interfaces configuradas.  
A URL fornecida pelo usuário é passada para a função Lambda.

### 2. **Geração da URL Encurtada:**
O **URLShortenerService** é acionado para gerar uma URL encurtada. O serviço cria um identificador único para a URL original (geralmente por meio de um algoritmo simples, como base64 ou um hash).  
Esse identificador é usado para construir a URL encurtada.

### 3. **Armazenamento no Amazon S3:**
A URL encurtada gerada é armazenada no **Amazon S3** através da classe **S3StorageService**.  
O S3 mantém o mapeamento entre a URL encurtada e a URL original, permitindo que o serviço seja escalável e resistente a falhas.

### 4. **Redirecionamento:**
Quando o usuário acessa a URL encurtada, o serviço verifica o mapeamento no S3.  
Se a URL encurtada for válida, o sistema faz um **redirecionamento** para a URL original.

Esse processo é eficiente e escalável, aproveitando as funcionalidades da AWS para garantir um desempenho ótimo e confiável.
