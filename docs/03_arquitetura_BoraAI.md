# Arquitetura do Sistema - BoraAI

## 1. Visão Geral
O **BoraAI** é uma plataforma Web gamificada focada em otimizar a jornada de aprendizagem de estudantes do Ensino Profissional e Tecnológico (EPT). O grande diferencial do sistema é a utilização de **RAG (Retrieval-Augmented Generation)**, permitindo que a IA consulte documentos institucionais (ementas, PDFs de aulas) para gerar cronogramas, resumos e quizzes 100% alinhados ao conteúdo real da instituição.

## 2. Stack Tecnológica
* **Frontend:** Next.js (React) + Tailwind CSS (Alta compatibilidade com ferramentas de Vibe Coding como v0.dev).
* **Backend:** Next.js API Routes (Serverless) para agilizar o deploy.
* **Banco de Dados:** Supabase (PostgreSQL) - Facilita a autenticação e possui suporte nativo a *pgvector* (essencial para o banco de dados vetorial do RAG).
* **IA & RAG:** OpenAI API (LLM) + LangChain (Orquestração) + Supabase Vector (Armazenamento de Embeddings).
* **Deploy:** Vercel (Integração contínua e CI/CD automáticos).

## 3. Diagrama Arquitetural e Fluxo de Dados (RAG)
O diagrama abaixo ilustra como o aluno interage com o sistema e como o RAG processa os documentos da instituição para gerar respostas inteligentes.

```mermaid
graph TD
    A[Estudante EPT] -->|Acessa WebApp| B(Frontend - Next.js)
    B -->|Solicita Resumo/Dúvida| C{Backend API}
    
    subgraph Motor de IA (RAG)
        C -->|1. Busca Semântica| D[(Supabase Vector DB)]
        D -->|2. Retorna Contexto do PDF| C
        C -->|3. Envia Contexto + Prompt| E[OpenAI API]
        E -->|4. Resposta Gerada| C
    end
    
    C -->|5. Exibe Resposta na Tela| B
    
    subgraph Gamificação
        C -.->|Registra XP / Streak| F[(Banco Relacional)]
    end
