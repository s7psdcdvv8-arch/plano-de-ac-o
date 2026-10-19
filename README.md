# Plano de ação: máquina de viralização

O lado de execução da máquina de viralização para o mercado imobiliário: como construir cada vídeo e o que publicar nos próximos 30 dias.

As referências e análises do que já performa ficam no repositório [conteudos-em-alta-no-imobiliario-](https://github.com/s7psdcdvv8-arch/conteudos-em-alta-no-imobiliario-). Este repositório transforma esse material em roteiros e planos.

## Estrutura

```
prompts/               Instruções prontas para o Claude
  instrucoes-plano-de-acao-30-dias.md     Papel, metodologia e formato do plano de 30 dias
guias/                 Como construir cada parte do vídeo
  01-tour-de-imoveis.md              Estruturas de tour (Quanto custa, POV, Lifestyle)
  02-takes-e-ganchos-de-retencao.md  Banco de ganchos de 0 a 3s e regras de corte
  03-atuacao-e-direcao-de-cena.md    Tom de voz, postura, enquadramento
  04-duvidas-e-dores-do-mercado.md   Pilares educativos e quebra de objeções
  05-motion-design.md                Estilos visuais, mapas animados, legendas
plano-30-dias/         Planos de conteúdo gerados
```

## Como usar com o Claude

- **Plano de 30 dias:** peça ao Claude para seguir `prompts/instrucoes-plano-de-acao-30-dias.md`, usando as referências e análises do repositório de conteúdos em alta e os guias deste repositório. O resultado vai para `plano-30-dias/`.
- **Roteiro avulso:** indique o tipo de vídeo (tour, educativo, comparativo) e o Claude escolhe a estrutura em `guias/` e um gancho em `guias/02-takes-e-ganchos-de-retencao.md`.
- **Direção visual:** cite `guias/05-motion-design.md`.
