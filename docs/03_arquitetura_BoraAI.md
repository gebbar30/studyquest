# Arquitetura do Sistema - BoraAI

## 1. Visão Geral
O **BoraAI** é uma plataforma Web gamificada focada em otimizar a jornada de aprendizagem de estudantes do Ensino Profissional e Tecnológico (EPT). O grande diferencial do sistema é a utilização de **RAG (Retrieval-Augmented Generation)**, permitindo que a IA consulte documentos institucionais, a plataforma web oficial e o App da escola para gerar cronogramas e tirar dúvidas baseadas no contexto real do aluno.

## 2. Stack Tecnológica
* **Frontend:** Next.js (React) + Tailwind CSS (Alta compatibilidade com ferramentas de Vibe Coding).
* **Backend:** Next.js API Routes (Serverless) para agilizar o deploy.
* **Banco de Dados:** Supabase (PostgreSQL) com suporte nativo a *pgvector*.
* **IA & RAG:** OpenAI API (LLM) + LangChain + Supabase Vector.
* **Deploy:** Vercel.

## 3. Diagrama Arquitetural e Fluxo de Dados (RAG)
O diagrama abaixo ilustra como o aluno interage com o sistema e como o RAG processa as múltiplas fontes da instituição.

```mermaid
graph TD
    A[Estudante EPT] -->|Acessa WebApp| B(Frontend - Next.js)
    B -->|Solicita Resumo/Dúvida| C{Backend API}
    
    subgraph Motor de IA RAG Expandido
        C -->|1. Busca Semântica| D[(Vector DB - Supabase)]
        C -->|Integração API| X[App/Plataforma Oficial]
        D -.->|Retorna Contexto PDF| C
        X -.->|Retorna Notas/Avisos| C
        C -->|2. Envia Contexto + Prompt| E[OpenAI API]
        E -->|3. Resposta Gerada| C
    end
    
    C -->|4. Exibe Resposta na Tela| B
    
    subgraph Gamificação
        C -.->|Registra XP / Streak| F[(Banco Relacional)]
    end
