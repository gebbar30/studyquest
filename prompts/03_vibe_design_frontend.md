# Engenharia de Prompt: Vibe Design (Frontend)

Este documento registra os comandos estruturados enviados para a IA (v0.dev / Bolt.new) para a geração do protótipo visual do MVP do **BoraAI**, cumprindo a exigência da Fase 2 (gerar telas, gerar navegação e criar dados mockados).

## 1. Prompt para o Dashboard Principal (Gamificação)

**Papel:** Atue como um Engenheiro Front-end Sênior e Especialista em UI/UX.
**Tarefa:** Crie a tela de Dashboard (Painel Principal) para uma plataforma web chamada "BoraAI", focada em estudantes do Ensino Profissional e Tecnológico (EPT).
**Restrições:** Use React, Tailwind CSS e ícones Lucide. O design deve ser moderno, limpo, no modo escuro (Dark Mode) e responsivo (Mobile-First).
**Requisitos Visuais (Dados Mockados):**
1. Sidebar lateral responsiva com navegação: Início, Tutor IA, Documentos, Meu Progresso.
2. Card de Perfil no topo: Nome do aluno (mockado: Jhonatas), Turno (EPT Noturno).
3. Sistema de Gamificação (Destaque): Barra de Progresso de XP (Ex: 850/1000 XP) e Nível atual (Ex: Nível 5 - Focado).
4. Card de "Streak" mostrando dias seguidos de estudo com ícone de fogo.
5. Seção central: "Missões de Estudo de Hoje" com botões de check para concluir tarefas mockadas.

---

## 2. Prompt para o Chat RAG (Tutor IA)

**Papel:** Atue como um Engenheiro Front-end Sênior especialista em interfaces conversacionais.
**Tarefa:** Crie a tela de Chat (Tutor IA) para a plataforma "BoraAI", onde o aluno interage com os documentos da instituição (RAG).
**Restrições:** Use React, Tailwind CSS. Mantenha o mesmo padrão visual (Dark Mode) do Dashboard. A interface deve ser focada na usabilidade de leitura.
**Requisitos Visuais (Dados Mockados):**
1. Cabeçalho mostrando "Tutor BoraAI - Baseado no Acervo da Instituição".
2. Área de chat principal com balões de diálogo.
3. Mensagem do Usuário mockada: "Quais os tópicos principais da ementa de Redes I?"
4. Mensagem da IA mockada: Resposta estruturada em tópicos com um pequeno selo abaixo dizendo "Fonte: Ementa_Redes_2026.pdf".
5. Barra inferior fixa para digitação da pergunta com botão de enviar (ícone de seta).
