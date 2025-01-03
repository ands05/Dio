# Segmentação de Instâncias com YOLOv11: Detecção de Cachorros e Gatos

Este repositório contém um modelo de segmentação de instâncias baseado no YOLOv11, treinado para identificar cachorros e gatos em imagens. Abaixo estão os detalhes do projeto e como utilizá-lo.

## Visão Geral
O modelo utiliza o YOLOv11 para segmentação de instâncias, permitindo detectar e segmentar objetos específicos em imagens. O modelo foi treinado com 484 imagens rotuladas e avaliado em um conjunto de validação com uma precisão média (mAP) de **83,3%**. As categorias detectadas pelo modelo incluem:

- **Cachorro**
- **Gato**

## Exemplos de Previsões

### Detecção de Cachorros
![Captura de Tela (104)](https://github.com/user-attachments/assets/ca774746-53e6-4972-ac6c-560e735e1638)
O modelo identifica cachorros com um alto nível de confiança (exemplo: 91% neste caso).

### Detecção de Gatos
![Captura de Tela (105)](https://github.com/user-attachments/assets/255e9c4e-5be5-4503-82ee-07e7c0dec544)
O modelo detecta gatos com precisão, como mostrado com confiança de 91% neste exemplo.

## Detalhes do Modelo
- **Tipo de Modelo:** YOLOv11 Segmentação de Instâncias (Rápido)
- **Treinado com:** 484 imagens
- **Checkpoint:** COCOn-seg

## Funcionalidades
- Segmentação de instâncias com rótulos de objetos e níveis de confiança.
- Ajuste personalizável do limite de confiança para previsões.

## Como Usar
1. **Envie Sua Imagem:** Utilize a seção "Upload Image" para adicionar uma nova imagem para segmentação.
2. **Visualize as Previsões:** O modelo exibirá as previsões com regiões segmentadas e pontuações de confiança.
3. **Integração via API:** Use a API fornecida para integrar o modelo em suas aplicações.

## Exemplo de Saída JSON
Abaixo está um exemplo da saída JSON para um cachorro detectado:

```json
{
  "predictions": [
    {
      "x": 145.5,
      "y": 189.5,
      "width": 263,
      "height": 369,
      "confidence": 0.913,
      "class": "dog",
      "points": [
        {"x": 102.513, "y": 5.625},
        {"x": 102.978, "y": 89.221},
        ...
      ]
    }
  ]
}
```

## Requisitos
Para usar o modelo localmente, você precisará de:
- Python 3.8+
- Bibliotecas necessárias: `torch`, `numpy`, `opencv-python`, `roboflow`

## Configuração e Instalação
1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   cd nome-do-repositorio
   ```
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute o script para testar previsões:
   ```bash
   python visualize.py --image caminho-da-sua-imagem
   ```

## Agradecimentos
Este projeto utiliza [Roboflow](https://roboflow.com/) para anotação e treinamento. Agradecimentos especiais à plataforma por facilitar a preparação do conjunto de dados e do modelo.
