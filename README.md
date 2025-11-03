# Jogo do Número Secreto

App web estática simples (Vanilla JS, HTML e CSS) — jogo para adivinhar um número secreto.

Principais arquivos
- `index.html` — interface (contém `h1`, `p`, `input`, botões). O script `app.js` é carregado com `defer`.
- `app.js` — lógica do jogo. Variáveis importantes: `numeroSecreto`, `numeroLimite`, `tentativas`, `listaNumerosSorteados`.
- `style.css` — estilos e responsividade.

Como executar localmente
- Abrir `index.html` no navegador (modo rápido).
- Usar o Live Server do VS Code (recomendado para live-reload).
- Alternativa com Python (porta 5500 neste exemplo):

```powershell
# a partir da raiz do projeto
python -m http.server 5500
# então abra http://localhost:5500
```

Padrões e pontos importantes
- Não editar os arquivos gerados pelo Live Server: `img/JS Game_files/` (são artefatos). Trabalhe nos arquivos da raiz.
- Seletores simples são usados em `app.js` (ex.: `document.querySelector('input')`, `document.querySelector(tag)`, `document.getElementById('reiniciar')`). Se renomear elementos no HTML, atualize o JS.
- O jogo usa `responsiveVoice` via CDN (incluso em `index.html`). Se for removê-lo, remova também as chamadas `responsiveVoice.speak(...)` em `app.js` ou forneça fallback.

Edições comuns
- Aumentar o limite do número:
  - editar `app.js` e ajustar `let numeroLimite = <novo_valor>`;
  - ajustar o `max` do `input` em `index.html` (ex.: `max="50"`).

Notas de desenvolvimento
- Não há pipeline de build, testes ou CI neste repositório. Se adicionar dependências, inclua um `package.json` e instruções no README.
- Logs: `app.js` faz `console.log(listaNumerosSorteados)` durante a geração para ajudar depuração.

Próximos passos sugeridos (me diga se quer que eu faça)
- Adicionar um `.gitignore` que exclua `img/JS Game_files/` e outros artefatos gerados.
- Modularizar `app.js` para ES Modules (se planejar evolução do projeto).
- Adicionar um pequeno conjunto de testes ou um script de verificação automática.

Problemas conhecidos / limitações
- Estado mantido em variáveis globais (simples, aceitável para este projeto didático, mas pode ser refatorado para testes/escala).