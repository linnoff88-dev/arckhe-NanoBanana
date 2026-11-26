# Design System - Supercurso Nano Banana

**Data:** 2025-12-26
**Baseado em:** FEP_STYLE_REFERENCE.md, CONTENT_STRUCTURE.md, LAYOUT_REFERENCE.md

---

## 1. Stack Tecnológico

```
Framework CSS:  Tailwind CSS 3.x (CDN)
JavaScript:     Vanilla JS
Fontes:         Google Fonts - Inter
Build:          HTML puro (sem build process)
Dark Mode:      Tailwind class-based (localStorage + system preference)
Hospedagem:     GitHub Pages
```

---

## 2. Identidade Visual por Trilha

| Trilha | Nome | Cor Primária | Emoji | Badge |
|--------|------|--------------|-------|-------|
| **Trilha 1** | Fundamentos | Emerald (#10B981) | 🎯 | FUNDAMENTOS |
| **Trilha 2** | Nano Banana Mastery | Blue (#3B82F6) | 📚 | NANO BANANA |
| **Trilha 3** | Filmmaking com IA | Purple (#8B5CF6) | 🎬 | FILMMAKING |

### Classes por Trilha

```css
/* Trilha 1 - Fundamentos */
Badge:      bg-emerald-500/20 text-emerald-400
Borda:      border-emerald-500/30
Gradiente:  from-emerald-900/30 to-dark-800
Texto:      text-emerald-400
Hover:      hover:border-emerald-400

/* Trilha 2 - Nano Banana */
Badge:      bg-blue-500/20 text-blue-400
Borda:      border-blue-500/30
Gradiente:  from-blue-900/30 to-dark-800
Texto:      text-blue-400
Hover:      hover:border-blue-400

/* Trilha 3 - Filmmaking */
Badge:      bg-purple-500/20 text-purple-400
Borda:      border-purple-500/30
Gradiente:  from-purple-900/30 to-dark-800
Texto:      text-purple-400
Hover:      hover:border-purple-400
```

---

## 3. Paleta de Cores

### Dark Mode (Padrêo)
| Nome | Código | Uso |
|------|--------|-----|
| `dark-900` | `#111827` | Fundo principal da página |
| `dark-800` | `#1f2937` | Cards, containers |
| `dark-700` | `#374151` | Elementos internos, hover states |
| `dark-600` | `#4b5563` | Bordas, divisores |

### Light Mode
| Nome | Código | Uso |
|------|--------|-----|
| Background | `#f8fafc` | Fundo principal |
| Cards | `#ffffff` | Cards, containers |
| Elementos | `#f1f5f9` | Elementos internos |
| Bordas | `#e2e8f0` | Bordas, divisores |

### Cores Semânticas
| Cor | Uso |
|-----|-----|
| `emerald-400/500` | Sucesso, positivo, "fazer" |
| `red-400/500` | Erro, alerta, "nêo fazer" |
| `blue-400/500` | Informaçêo, dados |
| `yellow-400/500` | Aviso, atençêo |
| `cyan-400/500` | Tech, dicas técnicas |

---

## 4. Estrutura de Arquivos

```
/curso/
├── index.html                    # Página principal do curso
├── trilha1/
│   ├── index.html               # Página da Trilha 1
│   ├── modulo-1-1.html          # O que é Geraçêo de Imagens com IA
│   ├── modulo-1-2.html          # Como os Modelos de IA "Veem"
│   ├── ...
│   └── modulo-1-10.html         # Projeto Prático
├── trilha2/
│   ├── index.html
│   └── ...
├── trilha3/
│   ├── index.html
│   └── ...
└── assets/
    └── (se necessário)
```

---

## 5. Estrutura de Módulo

```
1. HEADER
   └── Badge da trilha
   └── Título com emoji
   └── Descriçêo (1-2 linhas)

2. STATS BANNER
   └── 3-5 métricas-chave do módulo

3. CONCEITOS PRINCIPAIS (2-4 seções)
   └── Cada conceito em seçêo própria
   └── Ordem: mais importante primeiro

4. ELEMENTOS DE SUPORTE
   └── Exemplos práticos
   └── Comparações (fazer/nêo fazer)
   └── Dados e pesquisas

5. RESUMO/CHECKLIST
   └── Síntese dos pontos principais
   └── CTA para voltar ao curso
```

---

## 6. Tópicos Expansíveis (Accordion)

### Estrutura HTML

```html
<ul class="topics-list space-y-0.5">
  <li class="topic-item">
    <button class="topic-button w-full text-left px-4 py-1 bg-dark-700/50 hover:bg-dark-700 rounded-lg transition-colors font-medium text-neutral-200 flex items-center">
      <span class="text-emerald-400 mr-2">▸</span>
      📌 Nome do Tópico
    </button>

    <div class="topic-explanation hidden ml-6 mt-2 p-4 bg-emerald-900/20 rounded-lg border-l-4 border-emerald-500">
      <p class="text-sm mb-1.5 text-neutral-300">
        <strong class="text-emerald-400">O que é:</strong> Explicaçêo clara do conceito.
      </p>
      <p class="text-sm mb-1.5 text-neutral-300">
        <strong class="text-emerald-400">Por que:</strong> Benefícios e motivo de aprender.
      </p>
      <p class="text-sm text-neutral-300">
        <strong class="text-emerald-400">Conceitos:</strong> Termos e ideias relacionadas.
      </p>
    </div>
  </li>
</ul>
```

### Os 3 Campos Obrigatórios

Cada tópico expansível DEVE ter exatamente 3 campos:

1. **O que é:** Explicaçêo clara e direta do conceito
2. **Por que:** Benefícios, importância e motivo de aprender
3. **Conceitos:** Termos-chave, ideias relacionadas, dados

### Espaçamento Compacto

| Elemento | Classe | Valor |
|----------|--------|-------|
| Entre botões | `space-y-0.5` | 2px |
| Padding dos botões | `py-1` | 4px |
| Entre parágrafos | `mb-1.5` | 6px |
| Margem esquerda da explicaçêo | `ml-6` | 24px |

### JavaScript do Accordion

```javascript
document.addEventListener('click', function(e) {
  const topicButton = e.target.closest('.topic-button');
  if (topicButton) {
    const topicItem = topicButton.closest('.topic-item');
    const explanation = topicItem.querySelector('.topic-explanation');
    const arrow = topicButton.querySelector('span:first-child');

    if (explanation) {
      // Fechar outros tópicos do mesmo módulo
      const moduleCard = topicItem.closest('.module-card');
      moduleCard.querySelectorAll('.topic-explanation').forEach(exp => {
        if (exp !== explanation) {
          exp.classList.add('hidden');
          const otherArrow = exp.closest('.topic-item').querySelector('.topic-button span:first-child');
          if (otherArrow) otherArrow.textContent = '▸';
        }
      });

      // Toggle atual
      explanation.classList.toggle('hidden');
      arrow.textContent = explanation.classList.contains('hidden') ? '▸' : '▾';
    }
  }
});
```

---

## 7. Tipos de Boxes

### Box de Conceito (Gradiente)
```html
<div class="bg-gradient-to-br from-[COR]-900/30 to-dark-800 rounded-2xl p-8 border border-[COR]-500/30">
```

### Box Simples (Card)
```html
<div class="bg-dark-800 rounded-2xl p-8 border border-dark-600">
```

### Box de Informaçêo Interna
```html
<div class="bg-dark-700/50 rounded-xl p-6 mb-6">
```

### Box de Dica
```html
<div class="bg-[COR]-900/20 p-6 rounded-xl border border-[COR]-500/30">
  <h4 class="font-bold text-[COR]-400 mb-3">💡 Dica</h4>
  <p class="text-neutral-300">...</p>
</div>
```

### Grid de Comparaçêo
```html
<div class="grid md:grid-cols-2 gap-6">
  <div class="bg-emerald-900/20 p-6 rounded-xl border border-emerald-500/30">
    <h4 class="font-bold text-emerald-400 mb-4">✓ FAZER</h4>
    ...
  </div>
  <div class="bg-red-900/20 p-6 rounded-xl border border-red-500/30">
    <h4 class="font-bold text-red-400 mb-4">✗ NêO FAZER</h4>
    ...
  </div>
</div>
```

---

## 8. Estrutura de Modais

### CSS Base do Modal

```css
.modal {
  display: none;
  position: fixed;
  z-index: 100;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0,0,0,0.6);
  backdrop-filter: blur(4px);
}

.modal.active {
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal-content {
  background-color: #1f2937;
  margin: auto;
  padding: 0;
  width: 90%;
  max-width: 900px;
  max-height: 90vh;
  border-radius: 1rem;
  overflow: hidden;
  box-shadow: 0 20px 25px rgba(0,0,0,0.3);
}

.modal-header {
  padding: 1.5rem 2rem;
  border-bottom: 1px solid #374151;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.modal-body {
  padding: 2rem;
  overflow-y: auto;
  max-height: calc(90vh - 80px);
}

.close-modal {
  color: #9ca3af;
  font-size: 2rem;
  font-weight: 700;
  cursor: pointer;
}

.close-modal:hover {
  color: #ef4444;
}
```

### Estrutura do Conteúdo do Modal

O modal deve conter o **mesmo conteúdo completo** da página do módulo, adaptado para o formato modal:

```
1. INTRO
   └── Descriçêo do módulo
   └── Badges (duraçêo, tópicos, nível)

2. SEÇÕES DE CONTEÚDO (3-5 seções)
   └── Alternar entre gradientes e fundos neutros
   └── Cada seçêo com emoji + título + conteúdo

3. RESUMO/CHECKLIST
   └── O que você aprendeu
   └── Fontes (se houver)
```

### Componentes Internos dos Modais

**Cards com Borda Colorida:**
```html
<div class="bg-purple-900/20 p-4 rounded border-l-4 border-purple-400">
  <p class="font-bold text-purple-400 mb-2">Título</p>
  <p class="text-sm text-neutral-300">Conteúdo</p>
</div>
```

**Comparações Lado a Lado:**
```html
<div class="grid md:grid-cols-2 gap-4">
  <div class="bg-dark-800/50 p-4 rounded">
    <p class="font-semibold text-red-400 mb-2">⏰ Antes:</p>
    <ul class="text-xs text-neutral-300">
      <li>✗ Problema 1</li>
    </ul>
  </div>
  <div class="bg-emerald-900/20 p-4 rounded border border-emerald-500/30">
    <p class="font-semibold text-emerald-400 mb-2">✨ Agora:</p>
    <ul class="text-xs text-neutral-300">
      <li>✓ Soluçêo 1</li>
    </ul>
  </div>
</div>
```

**Tabelas:**
```html
<div class="overflow-x-auto">
  <table class="w-full text-xs">
    <thead>
      <tr class="border-b border-dark-600">
        <th class="text-left py-2 px-2 text-neutral-400">Coluna</th>
      </tr>
    </thead>
    <tbody class="text-neutral-300">
      <tr class="border-b border-dark-700">
        <td class="py-2 px-2">Dado</td>
      </tr>
    </tbody>
  </table>
</div>
```

### JavaScript do Modal

```javascript
function openModal(modalId) {
  const modal = document.getElementById(modalId);
  modal.classList.add('active');
  document.body.style.overflow = 'hidden';
}

function closeModal(modalId) {
  const modal = document.getElementById(modalId);
  modal.classList.remove('active');
  document.body.style.overflow = 'auto';
}

// Fechar ao clicar fora
document.addEventListener('click', function(e) {
  if (e.target.classList.contains('modal')) {
    e.target.classList.remove('active');
    document.body.style.overflow = 'auto';
  }
});

// Fechar com ESC
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') {
    const activeModals = document.querySelectorAll('.modal.active');
    activeModals.forEach(modal => {
      modal.classList.remove('active');
      document.body.style.overflow = 'auto';
    });
  }
});
```

---

## 9. Tipografia

| Elemento | Classes |
|----------|---------|
| Título da página (h1) | `text-4xl sm:text-5xl font-bold` |
| Título de seçêo (h2) | `text-2xl font-bold` |
| Título de sub-seçêo (h3) | `text-xl font-bold` |
| Parágrafo normal | `text-neutral-300` |
| Texto secundário | `text-neutral-400` |
| Badge | `text-sm font-semibold` |

---

## 10. Espaçamento

| Classe | Uso |
|--------|-----|
| `mb-12` | Entre seções principais |
| `mb-6` | Entre sub-seções |
| `mb-4` | Entre elementos dentro de uma seçêo |
| `p-8` | Padding de cards principais |
| `p-6` | Padding de boxes internos |
| `gap-6` | Espaço entre itens de grid |

---

## 11. Container Principal

```html
<main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
  <!-- Conteúdo -->
</main>
```

---

## 12. Tom de Voz

- **Direto e prático:** Sem enrolaçêo
- **Conversacional:** Como se falasse com um amigo
- **Confiante:** Afirmações claras, nêo "talvez" ou "pode ser"
- **Empolgante:** Usar destaques em **negrito** para pontos-chave
- **Parágrafos:** Máximo 3-4 linhas

---

## 13. Checklist de Enriquecimento por Conceito

- [ ] **Contexto:** Por que isso importa?
- [ ] **Explicaçêo técnica:** Como funciona?
- [ ] **Visualizaçêo:** Diagrama, barra, timeline
- [ ] **Exemplos:** Casos reais, prompts prontos
- [ ] **Comparaçêo:** Certo vs Errado
- [ ] **Dados:** Estatísticas com fonte
- [ ] **Aplicaçêo:** Como usar na prática

---

## 14. Emojis por Contexto

| Categoria | Emojis |
|-----------|--------|
| Conceito | 💡 🧠 📖 |
| Técnica | ⚙️ 🔧 🛠️ |
| Exemplo | 📝 ✏️ |
| Dica | 💡 ✨ |
| Alerta | ⚠️ ❌ |
| Sucesso | ✅ ✓ 🎉 |
| Foto/Imagem | 📷 🖼️ 🎨 |
| Vídeo | 🎬 📹 🎥 |
| IA | 🤖 🧠 |
