# 📚 BoraAI
*Transformando estudo em progresso gamificado com apoio de IA.*

---

## ⚠️ 1. O Problema
## Problema
Estudantes do Ensino Profissional e Tecnológico (EPT) possuem uma rotina acadêmica densa e acelerada. O principal problema não é a falta de informação, mas a **fragmentação dos dados**. 
Atualmente, o aluno precisa acessar múltiplas fontes isoladas (o App oficial da instituição para ver notas, a plataforma web para baixar PDFs, e grupos de mensagens para avisos) e tentar, mentalmente, organizar tudo isso em uma rotina de estudos. Essa sobrecarga cognitiva gera fricção, fazendo com que o aluno perca tempo gerenciando arquivos em vez de efetivamente estudar e absorver o conteúdo.

---

## 💡 2. Proposta de Valor
BoraAI é uma plataforma gamificada focada em estudantes do Ensino Profissional (EPT). Utilizando a tecnologia RAG (Inteligência Artificial que lê os documentos da instituição), o sistema automatiza o planejamento de estudos, tira dúvidas baseadas no material oficial e recompensa o aluno com XP.

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
