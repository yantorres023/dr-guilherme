# Estudo — recursos extras para o site do Dr. Guilherme (cardiologista)

Contexto: consultório particular em Coronel Fabriciano (MG), agendamento só pelo WhatsApp, site estático (sem backend). Público: adultos e idosos do Vale do Aço, muitos no celular Android.

Critérios para escolher um extra:
1. Resolve uma dúvida ou tarefa real do paciente antes ou depois da consulta, ou tira trabalho da secretária.
2. Funciona sem servidor (site estático no Vercel): nada de dados do paciente indo para servidor nosso.
3. Respeita a publicidade médica (Resolução CFM 2.336/2023): nada de promessa de resultado, sensacionalismo, "antes e depois" ou autopromoção; conteúdo educativo é permitido.
4. Toda informação clínica ou operacional ainda não confirmada pelo médico fica como placeholder `[PREENCHER: ...]` ou marcada como exemplo.

## Extras escolhidos (página 2 = site completo + estes blocos)

### 1. Agenda online (pedido de horário)
- Calendário dos próximos ~30 dias; dias de atendimento e horários são de EXEMPLO (marcar visivelmente "horários de exemplo — [PREENCHER: agenda real]"). Sugestão de exemplo: seg, qua e sex, 08:00–12:00 e 14:00–17:30, slots de 30 min; domingos e dias passados desabilitados.
- O paciente escolhe: tipo (Primeira consulta / Retorno / Exame — com select do exame), dia, horário, nome e, opcional, um período alternativo.
- Botão "Enviar pedido pelo WhatsApp": abre wa.me/PREENCHER_WHATSAPP com a mensagem pronta (tipo, data por extenso, horário, nome). Texto deixa claro que é um PEDIDO e que o consultório confirma.
- Botão secundário após escolher: "Adicionar lembrete ao calendário" gera um .ics do horário pedido marcado "(a confirmar)". Opcional, se couber bem.
- Não pedir sintomas nem dados de saúde no formulário de agenda.

### 2. Preparo para exames
- Abas ou acordeão por exame: ECG, Holter 24h, MAPA, Ecocardiograma, Teste ergométrico.
- Para cada um: o que é (1 frase), quanto tempo dura, como se preparar, o que levar, o que evitar. Orientações gerais e conservadoras, por exemplo:
  - ECG: sem preparo especial; evitar cremes/óleos no peito; roupa fácil de abrir.
  - Holter: tomar banho antes (não pode molhar o aparelho); roupa de botão; manter rotina; anotar no diário sintomas e horários.
  - MAPA: banho antes; não molhar o aparelho; durante cada medida, parar e deixar o braço relaxado e estendido; anotar atividades, sono e remédios no diário.
  - Ecocardiograma: em geral sem preparo; trazer exames anteriores.
  - Teste ergométrico: roupa confortável e tênis; refeição leve cerca de 2 h antes; não fumar nem tomar café nas horas anteriores; NÃO suspender remédios por conta própria — só se o médico orientar.
- Em todos: "Medicamentos: não suspenda nenhum remédio sem orientação do médico." e um placeholder `[PREENCHER: confirmar com o médico/laboratório o preparo e onde o exame é feito]`.

### 3. Diário da pressão arterial
- Mini-ferramenta: registrar data/hora, sistólica, diastólica, pulso (opcional), braço, observação.
- Dados ficam só no aparelho (localStorage, com try/catch; funciona sem ele). Dizer isso na tela.
- Mostra a lista, a média das medidas e um gráfico simples (SVG) das últimas leituras. SEM classificar ("normal/alta") e sem diagnóstico — texto: "Leve estes registros para a consulta; quem interpreta é o médico."
- "Como medir em casa": sentado 5 min em repouso, costas apoiadas, pés no chão, braço apoiado na altura do coração, bexiga vazia, sem café/cigarro/exercício 30 min antes, não conversar; 2 medidas com 1 min de intervalo.
- Ações: imprimir/salvar PDF (CSS de impressão), apagar tudo (com confirmação).
- Aviso de urgência perto: valores muito altos com sintomas (dor no peito, falta de ar, fraqueza de um lado, confusão) → 192 / pronto-socorro.

### 4. Ficha pré-consulta ("prepare sua consulta")
- Checklist interativo do que levar (documento com foto, exames anteriores, lista de remédios, relatórios, diário da pressão).
- Campos livres: motivo da consulta, sintomas e desde quando, remédios em uso (nome e dose), alergias, histórico familiar, dúvidas para o médico.
- Gera um resumo para IMPRIMIR ou salvar em PDF e levar. Não envia nada para servidor. Não oferecer envio por WhatsApp desses dados de saúde (é dado sensível; o paciente leva impresso ou mostra no celular).

### 5. Conteúdo educativo curto ("Para ler antes da consulta")
- 3 cartões informativos, sem promessas: "Como medir a pressão em casa" (liga ao diário), "Palpitações: quando vale marcar consulta", "Check-up do coração: o que costuma envolver". Texto geral, com o rodapé "Conteúdo informativo; não substitui a consulta."
- Opcional se a página já estiver longa: pode ser seção compacta.

## Extras avaliados e deixados de fora
- Depoimentos/avaliações de pacientes: a publicidade médica restringe; só com orientação do médico e regra do CRM. Fora.
- Pagamento online / preço da consulta: decisão do médico; consulta particular. Fora (no máximo placeholder).
- Agendamento com confirmação automática (Google Calendar, Doctoralia, iClinic): exige backend/conta e decisão do consultório. A agenda da página 2 é o protótipo do fluxo; dá para ligar a um sistema real depois.
- Chatbot de sintomas: risco clínico. Fora.
- Calculadora de risco cardiovascular: exige dados laboratoriais e interpretação; risco de autodiagnóstico. Fora.

## Navegação entre as páginas
- Página 1 (`/`): versão essencial. Ganha um seletor discreto no header "Essencial · Completa" e um bloco/chamada antes do rodapé apontando para `/completo`.
- Página 2 (`/completo`, arquivo `completo.html`): tudo da página 1 + os extras, com itens novos no menu e o mesmo seletor marcando "Completa".
