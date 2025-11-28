# Criptografia-keylogger
Repositório criado para realização das aulas de segurança da DIO/Santander

# 🐍 Projetos de Segurança em Python

Este repositório reúne dois projetos didáticos desenvolvidos em Python:  
1. **Keylogger Demo** – captura teclas pressionadas e registra em arquivo de log.  
2. **Criptografia de Arquivos** – criptografa e descriptografa arquivos `.txt` usando a biblioteca `cryptography`.

⚠️ **Aviso importante:** Estes projetos são apenas para fins educacionais. Não devem ser utilizados para monitorar terceiros ou criptografar dados sem consentimento.

---

## 🔑 Projeto 1: Keylogger Demo

### 🚀 Funcionalidades
- Captura teclas normais (letras, números, símbolos).
- Identifica teclas especiais (Enter, Esc, Tab, etc).
- Ignora teclas como Shift, Ctrl, Alt.
- Registra data e hora de cada tecla pressionada.
- Encerra automaticamente ao pressionar **ESC**.

### ▶️ Como executar
1. Instale as dependências:
   ```bash
   pip install pynput

- Execute o script:
python keylogger.py
- As teclas serão registradas em log.txt.
🔐 Projeto 2: Criptografia de Arquivos🚀 Funcionalidades- Gera uma chave única de criptografia (chave.key).

- Criptografa arquivos .txt em uma pasta especificada.
- Descriptografa os arquivos usando a mesma chave.
- Exemplo prático de uso da biblioteca cryptography.
  
▶️ Como executar- Instale as dependências:
pip install cryptography
- Crie um arquivo de teste em uma pasta, por exemplo:
test_files/teste.txt
- Rode o script de criptografia:
python criptografar.py
- → O arquivo será criptografado.
- Rode o script de descriptografia:
python descriptografar.py
- → O arquivo será restaurado ao conteúdo original.

📂 Estrutura do repositório
python-security-projects/
│
├── keylogger.py          # Script de captura de teclas
├── criptografar.py       # Script de criptografia
├── descriptografar.py    # Script de descriptografia
├── requirements.txt      # Dependências
└── README.md             # Documentação

📦 requirements.txt
pynput
cryptography


📚 Aprendizados
- Uso da biblioteca pynput para interação com teclado.
- Uso da biblioteca cryptography para criptografia simétrica.
- Boas práticas de manipulação de arquivos em Python.
- Estruturação de projetos e documentação no GitHub.
