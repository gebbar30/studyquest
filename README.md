# 📚 StudyQuest
*Transformando estudo em progresso gamificado com apoio de IA.*

---

## ⚠️ 1. O Problema
Estudantes universitários frequentemente têm dificuldade em manter consistência em suas rotinas de estudo. A ausência de planejamento estruturado, combinada com baixa motivação ao longo do semestre, leva à procrastinação e ao acúmulo de conteúdo antes de provas e avaliações e bastantes estresses.

Grande parte das ferramentas existentes de organização acadêmica não oferece engajamento contínuo nem recomendações inteligentes de planejamento. Como resultado, muitos estudantes estudam de forma desorganizada, o que impacta negativamente o desempenho acadêmico e o bem-estar.

---

## 💡 2. Proposta de Valor
O **StudyQuest** é uma plataforma de produtividade acadêmica gamificada que utiliza inteligência artificial para sugerir rotinas de estudo personalizadas, transformando o progresso acadêmico em uma experiência motivadora baseada em desafios, níveis e recompensas.

---

## 👥 3. Personas

### Persona 1 — Lucas, o universitário sobrecarregado
Lucas tem 21 anos e cursa Engenharia. Ele divide seu tempo entre faculdade, estágio e atividades pessoais. Apesar de querer manter uma rotina de estudos consistente, frequentemente deixa o conteúdo acumular e acaba estudando intensivamente apenas na semana das provas. Ele utiliza aplicativos de produtividade, mas rapidamente perde o interesse porque eles não oferecem motivação suficiente. Para Lucas, um sistema que combine cronogramas inteligentes gerados por IA com mecânicas de gamificação (XP e níveis) poderia transformar o estudo em uma experiência mais envolvente.

### Persona 2 — Mariana, a estudante disciplinada que busca eficiência
Mariana tem 19 anos e cursa Direito. Ela já possui o hábito de estudar regularmente, mas sente que poderia ser mais eficiente na forma como organiza seu tempo e prioridades. Ela se motiva ao visualizar progresso e conquistas. Uma plataforma que utilize IA para sugerir ajustes em sua rotina de estudo e ofereça sistemas de progresso gamificado poderia ajudá-la a manter consistência e melhorar sua produtividade.

> **Nota de Transparência (Vibe Coding):** Estas personas foram geradas 100% via IA utilizando técnicas de Engenharia de Prompt (Papel, Tarefa, Restrições e Formato). O prompt exato encontra-se na pasta `/prompts/01_criacao_personas.md` deste repositório.

---

## ⚙️ 4. Lista de Funcionalidades (MVP)

* **Autenticação:** Cadastro de usuário e Login seguro.
* **Gestão de Rotinas de Estudo:** Criar rotina, definir disciplinas e blocos de estudo.
* **Dashboard de Progresso:** Visão semanal de horas estudadas e progresso por disciplina.
* **Sistema de Gamificação:** Ganho de XP por sessão, níveis de progresso, *streak* (dias seguidos) e conquistas (badges).
* **Assistente de IA:** Geração de cronograma de estudo e sugestão de distribuição de disciplinas.

---

## 📝 5. User Stories (Épicos)
* **Como** estudante universitário, **quero** organizar minhas sessões de estudo **para** manter consistência ao longo do semestre.
* **Como** usuário da plataforma, **quero** receber sugestões de cronograma geradas por IA **para** planejar melhor minha rotina.
* **Como** usuário, **quero** ganhar XP ao concluir sessões de estudo **para** me manter motivado a continuar estudando.

---

## 🎮 6. Mecânicas de Gamificação
O sistema de progresso baseia-se em acúmulo de **XP (Experience Points)**:
* Sessão de estudo concluída: **+10 XP**
* *Streak* de 3 dias seguidos: **+25 XP**
* Conclusão da meta semanal: **+50 XP**

---

## 🤖 7. Uso de Inteligência Artificial
A IA será o motor principal para:
1. **Geração de Cronograma:** Recebe como *input* as disciplinas, o tempo disponível e os dias da semana, entregando como *output* um plano semanal otimizado.
2. **Sugestão de Melhorias:** Exemplo: *"Você estudou apenas 2 horas de cálculo esta semana. Considere adicionar uma sessão extra antes da prova de sexta-feira."*

---

## 🏗️ 8. Arquitetura Planejada (Vibe Coding Stack)
Pensando na facilidade de prototipação rápida com ferramentas como **v0.dev**, **Bolt.new** ou **Cursor**, a stack idealizada para a Fase 2 e 3 é:
* **Frontend e Backend:** Next.js (React) + Tailwind CSS.
* **Banco de Dados:** SQLite ou Supabase (PostgreSQL) para persistência leve.
