# 🤖 Chatbot RAG — Coordenação de Ensino do CIn/UFPE

Este projeto cria um chatbot com RAG (Retrieval-Augmented Generation) que responde a perguntas relacionadas à Coordenação de Ensino do CIn/UFPE, utilizando PDFs como base de conhecimento. A interface é construída com Gradio e utiliza a OpenAI API para busca e resposta contextual.

---

## 🚀 Como executar no Google Colab

### 1. Instale as dependências:

```bash
!pip install openai gradio tqdm
```

### 2. Configure sua chave de API da OpenAI:

```python
client = OpenAI(api_key=userdata.get('OPENAI_API_KEY'))
```

> 💡 Você pode usar `os.environ["OPENAI_API_KEY"]` para esconder a chave usando variáveis de ambiente.

### 3. Organize todos os arquivos PDF em uma pasta:

Você vai inserir a pasta e nomear como **input_pdfs** e colocar dentro da pasta **sample_data**:

```python
dir_pdfs = '/content/sample_data/input_pdfs'
```

### 4. Dê um nome à sua vector store (uma vez só):

```python
store_name = "my_vector_store"
```

### 5. Execute o chatbot com Gradio:

```python

Interface = gr.ChatInterface(
    response_output,
    type="messages"
)

Interface.launch(debug=True)

```

---

## 📄 Estrutura esperada dos arquivos

- **dir_pdfs:** Uma pasta que devem conter conteúdos relevantes sobre a Coordenação de Ensino ou órgão que você queira resolver.
- **response_output():** Função que envia as perguntas ao modelo e retorna a resposta com base nos PDFs da pasta **input_pdfs**.
- **Vector Store:** Armazena os embeddings dos documentos para recuperação por similaridade.

---

## 🧠 Tecnologias usadas

- [OpenAI API](https://platform.openai.com/): Contrução do agente;
- [Gradio](https://gradio.app/): Contrução da interface;
- Python 3.10 ou versões superiores: linguagem de programação para contrução do código;
- Google Colab: IDE para rodar o código.

---

## 🛡️ Segurança

- O assistente responde apenas com base nos PDFs.
- Para perguntas fora do escopo dos documentos o modelo responde com: **"Não sei informar!"**

---

## 📬 Exemplo de uso

**Pergunta:**
> Como faço para migrar de perfil curricular ?

**Resposta:**
> A migração de perfil é feita através do formulário no site [...]. Acesse o link em até 10 dias após o início do semestre.

---
