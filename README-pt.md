[🇬🇧] [Read in english](./README.md)

# Transferência de estilo neural com Redes Neurais

Este repositório contém um **caderno Jupyter** que implementa a técnica de 
**Neural Style Transfer (NST)**. O objetivo é combinar a estrutura de uma 
imagem de conteúdo com a aparência artística de uma imagem de estilo. O 
método utiliza a rede neural convolucional **VGG19**, pré-treinada, para 
extrair e manipular características de ambas as imagens.

## Características do Projeto

- Implementação de **Neural Style Transfer** baseada em *Deep Learning*.
- Utiliza **VGG19** para extração de features.
- Cálculo da **Matriz de Gram** para transferência de estilo.
- Otimização da imagem final utilizando **Adam**.
- Download das imagens de conteúdo e estilo durante a execução do caderno.

## Estrutura do Código

### 1. Carregamento da Rede VGG19

- Apenas a parte de **features** da rede é carregada.
- Os pesos do modelo são congelados para evitar novos treinamentos.

### 2. Carregamento e Processamento das Imagens

- As imagens de conteúdo e estilo são carregadas.
- Redimensionamento e normalização são aplicados para compatibilidade com a VGG19.

### 3. Extração de Features

- A imagem passa por camadas convolucionais específicas da VGG19.
- É gerado um mapeamento das camadas para **representações de conteúdo e estilo**.

### 4. Cálculo da Matriz de Gram

- A **Matriz de Gram** é calculada para medir a correlação entre filtros convolucionais 
da imagem de estilo.
- Essa etapa ajuda a capturar os padrões texturais da arte escolhida.

### 5. Otimização da Imagem Final

- A imagem inicial é ajustada iterativamente para minimizar as perdas de conteúdo e estilo.
- A função de perda combina:
  - **Perda de conteúdo** (diferença entre a representação do conteúdo na imagem 
  gerada e na original).
  - **Perda de estilo** (diferença entre as matrizes de Gram da imagem gerada e da 
  imagem de estilo).
- O **Adam Optimizer** é utilizado para realizar o ajuste dos pixels da imagem gerada.

## Dependências

Para rodar este projeto, é necessário instalar as seguintes bibliotecas:

```bash
pip install torch torchvision numpy matplotlib pillow
```

## Execução

Para executar o caderno Jupyter, siga os seguintes passos:

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/neural-style-transfer.git
   cd neural-style-transfer
   ```
2. Instale as dependências conforme indicado acima.
3. Execute o Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
4. Abra o arquivo `.ipynb` e execute as células sequencialmente.

> Para rodar diretamente no google colab, [clique aqui](https://colab.research.google.com/github/ericshantos/neural_style_transfer/blob/main/working_with_style_transfer.ipynb)

## Resultados

Ao final da execução, a imagem gerada apresentará a estrutura da imagem de conteúdo combinada com as características estilísticas da imagem de estilo. Essa abordagem é amplamente utilizada para aplicações artísticas, criação de filtros de imagem e geração de arte digital com inteligência artificial.

### Resultado obtido

![](./assets/result.png)

## Licença

Este projeto está licenciado sob a **MIT License**. Consulte o arquivo `LICENSE` para mais detalhes.
