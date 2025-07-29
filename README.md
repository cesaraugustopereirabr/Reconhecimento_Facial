# 🔍 Sistema de Reconhecimento Facial com DeepFace no Google Colab

Este projeto tem como objetivo realizar **reconhecimento facial em imagens com múltiplas pessoas**, utilizando a biblioteca [DeepFace](https://github.com/serengil/deepface). Ele foi desenvolvido e testado diretamente no Google Colab, com foco em **facilidade de uso e precisão** no reconhecimento.

---

## 📦 Funcionalidades

- Reconhece rostos em uma imagem com várias pessoas.
- Compara com uma **base de imagens de referência**, mesmo que contenha múltiplas imagens por pessoa.
- Exibe os nomes e a **distância de similaridade** (quanto menor, mais parecido).
- Usa o modelo **ArcFace**, mais robusto que o padrão.
- Permite **ajuste fino da sensibilidade** do reconhecimento via threshold.

---

## 🧠 Tecnologias Utilizadas

- [Python 3.11+](https://www.python.org/)
- [DeepFace](https://github.com/serengil/deepface)
- [OpenCV](https://opencv.org/)
- [NumPy](https://numpy.org/)
- [Google Colab](https://colab.research.google.com)

---

## 📂 Estrutura de Pastas


- Todas as imagens de referência devem ser colocadas na pasta `faces_referencia/`.
- Use nomes no formato `nome_1.jpg`, `nome_2.jpg`, etc. O script agrupará todos os arquivos com o mesmo nome-base (`Lula`, `Sergey Lavrov`, etc).

---

## ⚙️ Como Funciona

1. O usuário faz upload de imagens de referência para cada pessoa a ser reconhecida.
2. O sistema gera **vetores de embedding facial** usando o modelo `ArcFace`.
3. Em seguida, o usuário envia uma imagem principal contendo vários rostos.
4. O sistema detecta os rostos, extrai seus vetores e **compara com todos os da base**.
5. O nome mais próximo (com menor distância Euclidiana) é atribuído ao rosto, se estiver abaixo de um **threshold** ajustável.

---

## 🧪 Exemplo Visual

<p align="center">
  <img src="exemplo_resultado.png" alt="Exemplo de Reconhecimento Facial" width="600"/>
</p>

---

## ⚠️ Possíveis Erros e Soluções

- **`KeyError: 'embedding'`**: O rosto não foi detectado corretamente. Aumente a qualidade da imagem.
- **`ImportError: cannot import name 'functions'`**: Versão antiga da biblioteca. O código já foi atualizado para não usar essa dependência.
- **`extract_faces() got an unexpected keyword`**: Foi removido o argumento `target_size` que não é mais aceito em versões recentes.

---

## 🔧 Parâmetros Importantes

| Parâmetro     | Descrição                                      | Valor Padrão |
|---------------|------------------------------------------------|---------------|
| `model_name`  | Modelo de reconhecimento facial usado          | `ArcFace`     |
| `threshold`   | Limite de distância para considerar um rosto reconhecido | `13`     |
| `enforce_detection` | Permite ou não forçar a detecção (pode evitar falhas em imagens com rosto parcial) | `False` |

---

## 🚀 Como Executar no Google Colab

1. Abra o Colab em: https://colab.research.google.com/
2. Copie e cole o código do notebook.
3. Faça o upload das imagens quando solicitado.
4. Veja o resultado diretamente no Colab.

---

## 📌 Próximos Passos (Melhorias Futuras)

- Exportar a imagem final com anotações.
- Adicionar verificação de identidade com `DeepFace.verify()`.
- Criar interface web com Streamlit.
- Suporte para vídeo em tempo real com OpenCV.

---

## 👨‍💻 Autor

**Cesar Augusto Pereira**  
Advogado | Estudante de Ciência de Dados e Engenharia da Computação

---

## 📜 Licença

Este projeto é livre para uso educacional e experimental. Não utilizar em contextos comerciais sem permissão prévia.
