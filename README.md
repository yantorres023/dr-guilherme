# Dr. Guilherme · Cardiologista — propostas de site

Duas propostas de site para o consultório do Dr. Guilherme Henrique Figueiredo de Oliveira (CRM-MG 48540, RQE 40142), em Coronel Fabriciano (MG). Cada design tem duas páginas:

- **Essencial** (`index.html`): o site institucional.
- **Completa** (`completo.html`): o mesmo site, com recursos extras.

As duas páginas são ligadas pelo seletor "Essencial · Completa" no topo.

No ar (GitHub Pages): https://yantorres023.github.io/dr-guilherme/

| Design | Estilo | Essencial | Completa |
|---|---|---|---|
| 2 | Claro, creme e terracota | [design-2/](https://yantorres023.github.io/dr-guilherme/design-2/) | [design-2/completo](https://yantorres023.github.io/dr-guilherme/design-2/completo) |
| 3 | Escuro, vinho e dourado | [design-3/](https://yantorres023.github.io/dr-guilherme/design-3/) | [design-3/completo](https://yantorres023.github.io/dr-guilherme/design-3/completo) |

## Estrutura

```
index.html              página inicial com os dois designs
design-2/index.html     design 2, versão essencial
design-2/completo.html  design 2, versão completa
design-3/index.html     design 3, versão essencial
design-3/completo.html  design 3, versão completa
ESTUDO-EXTRAS.md        estudo que definiu os recursos da versão completa
```

Cada página é um HTML único, com CSS e JS embutidos. Não há build nem dependências: basta abrir o arquivo ou servir a pasta.

## Recursos da versão completa

O estudo completo está em [ESTUDO-EXTRAS.md](ESTUDO-EXTRAS.md).

- **Agenda online:** o paciente escolhe tipo, dia e horário e o pedido abre no WhatsApp com a mensagem pronta. É um pedido; o consultório confirma.
- **Preparo para exames:** orientações para ECG, Holter, MAPA, ecocardiograma e teste ergométrico.
- **Diário da pressão:** registros com média e gráfico. Os dados ficam só no aparelho e o diário pode ser impresso.
- **Ficha pré-consulta:** checklist e resumo para imprimir e levar à consulta.
- **Para ler antes da consulta:** 3 textos informativos curtos.

Nenhum dado do paciente vai para servidor.

## Antes de publicar para valer

Tudo que está em amarelo tracejado (`[PREENCHER: ...]`) precisa ser confirmado com o médico:

- número do WhatsApp (`PREENCHER_WHATSAPP` nos links `wa.me`);
- dias e horários reais da agenda (os atuais são de exemplo);
- preparo de cada exame e onde é feito;
- foto, formação, convênios, teleconsulta e diretor técnico.
