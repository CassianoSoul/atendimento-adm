# Alô, SAC! Central do Caos (jogo de cartas)

Jogo de cartas sobre atendimento ao público. Funciona 100% offline: não precisa de servidor, chave ou internet.

## Como abrir
- Arquivo único: dê dois cliques em `alo-sac-offline.html`.
- Em pasta: abra `public/index.html` (usa `style.css` e `game.js` ao lado).

## Para colocar em um site
Envie a pasta `public` (ou o `alo-sac-offline.html`) para qualquer hospedagem de sites estáticos (Vercel, Netlify, GitHub Pages...). Não há backend.

## Como funciona
- 13 clientes, cada um com objetivo, 3 passos de solução, pergunta, carta de humor e carta ruim próprias.
- A cada vez saem 4 cartas (passo, pergunta ou empatia, humor/firmeza/coringa, e uma carta ruim ou de enrolação).
- Tempo para escolher: cerca de 12 s no nível 1, caindo até 8 s a partir do nível 5.
- Armadilhas: cartas que parecem profissionais mas são erradas (lista `TRAPS`), passos fora de ordem e clientes irritados (`ANG`) que exigem empatia antes de qualquer instrução.
- Chefe: Jefferson.
- Voz dos clientes: usa as vozes do navegador (speechSynthesis).
- Para editar falas: `DC` (cartas e reações de cada cliente), `DQ` (comentários extras) e as listas `GE`, `GF`, `GH`, `GB`, `GN` (cartas genéricas) no `public/game.js`.

## Memória contra repetição
O jogo guarda no navegador (localStorage) quais cartas e clientes já apareceram. As cartas só voltam depois que as outras do mesmo tipo já saíram, e os clientes seguem uma fila que não repete o mesmo cliente por pelo menos 7 ligações. Para zerar essa memória, limpe os dados do site ou apague as chaves `sacu` e `sacq`.
