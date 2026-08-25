# Parking_Intelligence
Análise inteligente de ocupação de estacionamentos com Python, visão computacional, KPIs e geração de insights para tomada de decisão.


# Parking_Intelligence

Um sistema de **Visão Computacional em Tempo Real** desenvolvido em Python e OpenCV para monitoramento inteligente de estacionamentos, realizando a identificação automática de vagas **livres e ocupadas** a partir de imagens ou vídeos.

## Demonstração

![Demonstração do Parking_Intelligence](demo_Parking_Intelligence_reduzido.gif)

O projeto utiliza técnicas de processamento digital de imagens, análise de regiões de interesse (ROI) e classificação visual para identificar o estado das vagas em tempo real.


# Parking_Intelligence

Um sistema de **Visão Computacional em Tempo Real** desenvolvido em Python e OpenCV para monitoramento inteligente de estacionamentos, realizando a identificação automática de vagas **livres e ocupadas** a partir de imagens ou vídeos.

O projeto utiliza técnicas de processamento digital de imagens, análise de regiões de interesse (ROI) e classificação visual para identificar o estado das vagas em tempo real.

---

## 🌟 Funcionalidades

* **Monitoramento em Tempo Real:** processamento contínuo de imagens ou vídeos para análise das vagas.
* **Detecção de Ocupação:** identificação automática de vagas livres e ocupadas.
* **Painel de Monitoramento:** apresentação das informações de ocupação do estacionamento.
* **Identificação Visual:** indicação do status de cada vaga diretamente na imagem.
* **Mapeamento de Vagas:** definição das áreas correspondentes às vagas para análise individual.
* **Persistência das Configurações:** armazenamento das posições cadastradas para reutilização.
* **Processamento Otimizado:** utilização de OpenCV e NumPy para processamento eficiente.
* **Estrutura Modular:** organização preparada para futuras melhorias e integração com Inteligência Artificial.

---

## 🛠️ Tecnologias Utilizadas

* **Python 3.x**
* **OpenCV:** processamento de imagens e vídeos.
* **NumPy:** manipulação de matrizes e dados de imagem.
* **Pillow:** renderização de elementos gráficos e textos.
* **JSON/Pickle:** armazenamento das configurações das vagas.
* **Git:** controle de versão.

---

## 🚀 Como Executar o Projeto

### 1. Instalar as dependências

```bash
pip install -r requirements.txt
```

### 2. Configurar o mapeamento das vagas

Execute a ferramenta responsável pelo cadastro das áreas:

```bash
python SpaceMapper.py
```

Utilize o mouse para definir as regiões correspondentes às vagas.

* **Botão esquerdo:** adiciona uma vaga.
* **Botão direito:** remove uma vaga.
* **Salvar:** armazena as posições configuradas.

### 3. Executar o sistema

Depois de realizar o mapeamento:

```bash
python main.py
```

O sistema iniciará o processamento da imagem ou vídeo e apresentará o estado das vagas em tempo real.

---

## 🔬 Pipeline de Visão Computacional

O processamento da imagem segue uma sequência de etapas:

```text
Frame Original
      │
      ▼
Conversão de Imagem
      │
      ▼
Escala de Cinza
      │
      ▼
Redução de Ruído
      │
      ▼
Binarização
      │
      ▼
Tratamento Morfológico
      │
      ▼
Definição das Regiões de Interesse
      │
      ▼
Análise das Regiões
      │
      ▼
Classificação
      │
      ├──────────────► LIVRE
      │
      └──────────────► OCUPADA
      │
      ▼
Atualização do Monitoramento
```

### Principais técnicas

**Escala de Cinza**

Transformação da imagem para um único canal, simplificando o processamento.

**Gaussian Blur**

Suavização da imagem para reduzir ruídos antes da análise.

**Threshold Adaptativo**

Processo de binarização utilizado para destacar características relevantes da imagem.

**Operações Morfológicas**

Tratamento da imagem para reduzir ruídos e melhorar as regiões identificadas.

**Região de Interesse (ROI)**

Cada vaga possui uma área específica utilizada para realizar a análise.

**Análise de Pixels**

Avaliação dos pixels presentes em cada região para auxiliar na classificação do estado da vaga.

---

## 📊 Monitoramento

O sistema pode apresentar informações como:

* **Total de vagas**
* **Vagas livres**
* **Vagas ocupadas**
* **Percentual de ocupação**
* **Percentual de disponibilidade**
* **Status individual das vagas**

As informações são atualizadas conforme o processamento dos frames.

---

## 🧠 Estrutura do Projeto

```text
Parking_Intelligence/
│
├── main.py
├── SpaceMapper.py
├── requirements.txt
├── README.md
│
├── data/
│   └── parking_spaces.json
│
├── assets/
│   └── parking_video.mp4
│
├── src/
│   ├── detector.py
│   ├── processor.py
│   ├── metrics.py
│   └── interface.py
│
└── output/
    └── screenshots/
```

A estrutura modular facilita a manutenção do código e permite a evolução do sistema.

---

## 📈 Aplicações

O **Parking_Intelligence** pode ser utilizado como base para:

* Monitoramento inteligente de estacionamentos;
* Identificação de disponibilidade de vagas;
* Análise de ocupação;
* Controle operacional;
* Estudos de Visão Computacional;
* Projetos de Inteligência Artificial;
* Desenvolvimento de sistemas inteligentes de estacionamento.

---

## 🚀 Roadmap

### Fase 1 — Visão Computacional

* [x] Processamento de imagens;
* [x] Processamento de vídeo;
* [x] Mapeamento das vagas;
* [x] Identificação de vagas livres e ocupadas;
* [x] Monitoramento visual.

### Fase 2 — Inteligência Artificial

* [ ] Integração com modelos de detecção de objetos;
* [ ] Detecção automática de veículos;
* [ ] Maior independência das posições previamente cadastradas;
* [ ] Maior robustez em diferentes ângulos de câmera;
* [ ] Melhor desempenho em diferentes condições de iluminação.

### Fase 3 — Integração

* [ ] API;
* [ ] Banco de dados;
* [ ] Dashboard web;
* [ ] Histórico de ocupação;
* [ ] Monitoramento remoto;
* [ ] Integração com ferramentas de análise.

### Fase 4 — Evolução

* [ ] Suporte a câmeras em diferentes posições;
* [ ] Processamento de câmeras IP;
* [ ] Monitoramento de múltiplos ambientes;
* [ ] Análise histórica;
* [ ] Arquitetura preparada para processamento contínuo.

---

## ⚠️ Limitações

A versão inicial utiliza técnicas tradicionais de processamento digital de imagens. Por isso, o desempenho pode variar de acordo com:

* Condições de iluminação;
* Sombras;
* Reflexos;
* Chuva;
* Posicionamento da câmera;
* Alterações no enquadramento;
* Obstruções nas vagas;
* Características do ambiente monitorado.

Essas limitações fazem parte do processo de evolução do projeto e podem ser reduzidas posteriormente com técnicas de **Machine Learning e Deep Learning**.

---

## 🎯 Objetivo do Projeto

O **Parking_Intelligence** tem como objetivo demonstrar a aplicação prática de **Visão Computacional e processamento digital de imagens** para transformar imagens de um estacionamento em informações sobre disponibilidade e ocupação de vagas.

O projeto também estabelece uma base para futuras evoluções envolvendo **Inteligência Artificial, APIs, bancos de dados, monitoramento remoto e análise inteligente de informações**.

> **Imagem → Processamento → Detecção → Classificação → Informação**
