# Guia de Prompts Veo 3.1 - Workflow com Nano Banana

## Visêo Geral do Veo 3.1
Veo 3.1 é o modelo de geraçêo de vídeo mais avançado do Google, com controles criativos de nível profissional, múltiplos aspect ratios e áudio sincronizado rico.

## Capacidades Principais

### Recursos de Geraçêo Core
- **Vídeo de alta fidelidade**: 720p ou 1080p
- **Aspect ratio**: 16:9 ou 9:16
- **Duraçêo variável**: Clips de 4, 6 ou 8 segundos
- **Áudio rico e diálogo**: Gera som sincronizado realista, desde conversas multi-pessoa até efeitos sonoros
- **Compreensêo de cena complexa**: Entendimento profundo de estrutura narrativa e estilos cinematográficos

### Controles Criativos Avançados
- **Image-to-video melhorado**: Animar imagem fonte com maior aderência ao prompt
- **Ingredients to video**: Fornecer imagens de referência para manter estética consistente
- **First and last frame**: Gerar transiçêo natural entre imagem inicial e final
- **Add/remove object**: Introduzir ou remover objetos de vídeo gerado

## Fórmula para Prompts Eficazes

**[Cinematografia] + [Sujeito] + [Açêo] + [Contexto] + [Estilo & Ambiente]**

### Elementos da Fórmula
1. **Cinematografia**: Defina o trabalho de câmera e composiçêo do plano
2. **Sujeito**: Identifique o personagem principal ou ponto focal
3. **Açêo**: Descreva o que o sujeito está fazendo
4. **Contexto**: Detalhe o ambiente e elementos de fundo
5. **Estilo & Ambiente**: Especifique a estética geral, humor e iluminaçêo

### Exemplo de Prompt
"Medium shot, a tired corporate worker, rubbing his temples in exhaustion, in front of a bulky 1980s computer in a cluttered office late at night. The scene is lit by the harsh fluorescent overhead lights and the green glow of the monochrome monitor. Retro aesthetic, shot as if on 1980s color film, slightly grainy."

## Técnicas Essenciais de Prompting

### Linguagem de Cinematografia
- **Movimento de câmera**: Dolly shot, tracking shot, crane shot, aerial view, slow pan, POV shot
- **Composiçêo**: Wide shot, close-up, extreme close-up, low angle, two-shot
- **Lente & Foco**: Shallow depth of field, wide-angle lens, soft focus, macro lens, deep focus

### Direcionando o Som
- **Diálogo**: Use aspas para fala específica (ex: A woman says, "We have to leave now.")
- **Efeitos sonoros (SFX)**: Descreva sons com clareza (ex: SFX: thunder cracks in the distance)
- **Ruído ambiente**: Defina a paisagem sonora de fundo

### Prompts Negativos
Descreva o que deseja excluir de forma positiva. Ex: "a desolate landscape with no buildings or roads"

## Workflows Avançados com Nano Banana

### Workflow 1: Transiçêo Dinâmica com "First and Last Frame"

**Passo 1 - Criar frame inicial** (Gemini 2.5 Flash Image/Nano Banana):
"Medium shot of a female pop star singing passionately into a vintage microphone. She is on a dark stage, lit by a single, dramatic spotlight from the front. Photorealistic, cinematic."

**Passo 2 - Criar frame final** (Nano Banana):
"POV shot from behind the singer on stage, looking out at a large, cheering crowd. The stage lights are bright, creating lens flare. Energetic atmosphere."

**Passo 3 - Animar com Veo** (First and Last Frame):
"The camera performs a smooth 180-degree arc shot, starting with the front-facing view of the singer and circling around her to seamlessly end on the POV shot."

### Workflow 2: Cena de Diálogo com "Ingredients to Video"

**Passo 1**: Gerar imagens de referência para personagens e cenário usando Nano Banana
**Passo 2**: Usar Ingredients to Video com as imagens de referência
**Passo 3**: Compor a cena com diálogo no prompt

### Workflow 3: Timestamp Prompting

Permite dirigir uma sequência completa com pacing cinematográfico preciso em uma única geraçêo:

```
[00:00-00:02] Medium shot from behind a young female explorer...
[00:02-00:04] Reverse shot of the explorer's freckled face...
[00:04-00:06] Tracking shot following the explorer...
[00:06-00:08] Wide, high-angle crane shot...
```

## Tendências Virais 2025 - Nano Banana + Veo 3

### Tipos de Conteúdo Viral
1. **Selfies com celebridades**: Vídeos AI de selfies com famosos
2. **Vídeos de produtos CGI**: Anúncios virais de produtos
3. **Restauraçêo de fotos antigas**: Transformar fotos de infância em vídeos
4. **UGC-style ads**: Anúncios estilo influenciador
5. **Storyboards cinematográficos**: Visualizaçêo de cenas de filmes
