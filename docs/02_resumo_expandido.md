# Resumo Expandido: BoraAI - Plataforma Gamificada e Inteligente para o EPT

## 1. Introdução
O Ensino Profissional e Tecnológico (EPT) exige dos estudantes um ritmo acelerado, conciliando teoria e prática técnica. No entanto, a fragmentação de informações (PDFs, portais, grupos de avisos) gera sobrecarga cognitiva, resultando em procrastinação e baixo desempenho. Diante desse cenário, utilizando o paradigma do Vibe Coding, surge o "BoraAI". O projeto une Gamificação (para retenção e motivação) à Inteligência Artificial com arquitetura RAG (Retrieval-Augmented Generation), permitindo que a IA atue como um tutor que lê os documentos reais da instituição para guiar o aluno.

## 2. Objetivos
**Objetivo Geral:** Desenvolver o protótipo funcional (MVP) de uma plataforma web gamificada focada na organização acadêmica de estudantes do EPT, utilizando IA (RAG) e metodologias de Vibe Coding.

**Objetivos Específicos:**
* Mapear perfis de estudantes técnicos e suas dores reais utilizando IA Generativa.
* Implementar arquitetura RAG para permitir que a IA consulte ementas e materiais da escola.
* Projetar mecânicas de gamificação (XP e Níveis) validadas via protótipos de UI (v0.dev).
* Estruturar a arquitetura de software focada em Next.js e Supabase (pgvector).

## 3. Personas
**Persona 1 — Lucas, o aluno técnico sobrecarregado**
Lucas tem 19 anos e cursa o Técnico em Redes de Computadores no turno noturno. Ele trabalha de dia e estuda à noite. Seu maior problema não é a falta de vontade, mas a perda de tempo procurando qual PDF ou ementa ele deve ler para a prova. Para Lucas, o BoraAI é essencial pois a IA resume o material oficial da escola e entrega o que ele precisa estudar, enquanto a gamificação o mantém acordado e motivado.

**Persona 2 — Mariana, a estudante que busca eficiência**
Mariana tem 20 anos e cursa Técnico em Logística. Ela é organizada, mas sente dificuldade em tirar dúvidas rápidas quando está estudando em casa. Uma plataforma com um "Tutor IA" treinado exclusivamente com os regimentos e manuais da sua instituição a ajudaria a ter respostas confiáveis imediatamente, melhorando sua produtividade.

## 4. Lista de Funcionalidades (MVP)
* **Autenticação:** Cadastro de usuário e Login seguro.
* **Tutor IA (Motor RAG):** Chat inteligente que responde dúvidas baseando-se no acervo documental da instituição.
* **Dashboard Gamificado:** Visão de missões diárias, progresso de XP, níveis e ofensiva (streak).
* **Integração de Fontes:** Upload de PDFs e conexão com a plataforma oficial.

## 5. User Stories (Épicos)
* Como estudante do EPT, quero organizar minhas missões de estudo diárias para manter consistência.
* Como usuário, quero fazer perguntas ao Tutor IA sobre o material da aula, para tirar dúvidas sem precisar ler o PDF inteiro.
* Como usuário, quero ganhar XP e manter minha "ofensiva" (streak) ao concluir tarefas para me sentir motivado.

## 6. Mecânicas de Gamificação
O sistema de progresso baseia-se em acúmulo de XP (Experience Points):
* Sessão de estudo/Leitura concluída: +10 XP
* Streak (Ofensiva) mantida diariamente: +25 XP
* Conclusão de todas as missões semanais: +50 XP

## 7. Uso de Inteligência Artificial
A IA será o motor principal da plataforma através de duas frentes:
1. **Arquitetura RAG (Tutor Institucional):** A IA recebe a dúvida do aluno, busca a informação diretamente no banco de dados vetorial (onde estão os PDFs da escola) e gera uma resposta citando a fonte exata.
2. **Geração de Missões:** A IA quebra um conteúdo denso em pequenas "missões de estudo" diárias adaptadas ao turno do aluno.
