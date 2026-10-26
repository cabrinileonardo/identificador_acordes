# 🎹 Identificador de Acordes MIDI

Projeto apresentado na **Feira de Profissões da Uniara**.
Você conecta um teclado MIDI no computador, toca um acorde e o programa mostra na hora qual acorde foi tocado.

## Como funciona

```
Teclado MIDI ──USB──▶ Python + Mido ──▶ notas pressionadas ──▶ identificação ──▶ nome do acorde na tela
```

1. O teclado envia mensagens `note_on` / `note_off` a cada tecla pressionada ou solta
2. O programa converte o número MIDI na nota (C, C#, D…), tratando as oitavas com **módulo 12**
3. Cada nota tocada é testada como fundamental, e o conjunto de **intervalos em semitons** é comparado com as fórmulas de acordes

## O que reconhece

- **Tríades:** maior, menor, diminuta, aumentada, sus2 e sus4
- **Tétrades:** maj7, 7 (dominante), m7, mMaj7, dim7, meio-diminuto (m7b5), aug7, 6 e m6
- Em **qualquer tonalidade e inversão**, já que a fundamental é descoberta pelos intervalos

## Interface

- Janela em **Tkinter** com o acorde identificado, as notas pressionadas e o status da conexão
- **Piano virtual de 88 teclas** (A0 a C8), desenhado em `Canvas`, que acende as teclas tocadas
- Também dá pra tocar notas **clicando no piano virtual** com o mouse (uma por vez), útil pra testar sem teclado
- Botão para escolher e conectar o dispositivo MIDI, com aviso quando nenhum é encontrado

## Como rodar

```bash
pip install -r requirements.txt
python main.py
```

Requer Python 3. As bibliotecas são `mido` e `python-rtmidi`; o Tkinter já vem com o Python.

## Tecnologias

Python · Mido · python-rtmidi · Tkinter · Git/GitHub

---

Projeto acadêmico · Leonardo Cabrini Mauro · [LinkedIn](https://www.linkedin.com/in/leonardo-cabrini-mauro-79b292355/)
