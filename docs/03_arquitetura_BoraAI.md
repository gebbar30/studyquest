# Arquitetura do Sistema - BoraAI

## 1. Visão Geral
O **BoraAI** é uma plataforma Web gamificada focada em otimizar a jornada de aprendizagem de estudantes do Ensino Profissional e Tecnológico (EPT). O grande diferencial do sistema é a utilização de **RAG (Retrieval-Augmented Generation)**, permitindo que a IA consulte documentos institucionais, a plataforma web oficial e o App da escola para gerar cronogramas e tirar dúvidas baseadas no contexto real do aluno.

## 2. Stack Tecnológica
* **Frontend:** Next.js (React) + Tailwind CSS
* **Backend:** Next.js API Routes (Serverless)
* **Banco de Dados:** Supabase (PostgreSQL) com suporte a pgvector
* **IA & RAG:** OpenAI API (LLM) + LangChain + Supabase Vector
* **Deploy:** Vercel

## 3. Diagrama Arquitetural e Fluxo de Dados (RAG)
O diagrama abaixo ilustra como o aluno interage com o sistema e como o RAG processa as múltiplas fontes da instituição.

```mermaid
graph TD
    A[Estudante EPT] -->|Acessa WebApp| B(Frontend - Next.js)
    B -->|Solicita Resumo ou Duvida| C{Backend API}
    
    subgraph IA [Motor de IA]
        D[(Vector DB - Supabase)]
        X[App ou Plataforma Oficial]
        E[OpenAI API]
    end
    
    subgraph BD [Gamificacao]
        F[(Banco Relacional)]
    end
    
    C -->|1. Busca Semantica| D
    C -->|Integracao API| X
    D -.->|Retorna Contexto PDF| C
    X -.->|Retorna Notas ou Avisos| C
    C -->|2. Envia Contexto e Prompt| E
    E -->|3. Resposta Gerada| C
    
    C -->|4. Exibe Resposta na Tela| B
    C -.->|Registra XP| F
```

## 4. Diagrama de Entidade-Relacionamento
Estrutura enxuta para validação do MVP.

```mermaid
erDiagram
    USUARIO {
        uuid id PK
        string nome
        string turno
        int xp_total
    }
    FONTE_DADOS {
        uuid id PK
        string tipo_fonte "PDF_App_Web"
        string url_ou_arquivo
    }
    SESSAO_ESTUDO {
        uuid id PK
        uuid usuario_id FK
        int xp_ganho
    }
    USUARIO ||--o{ SESSAO_ESTUDO : realiza
    FONTE_DADOS ||--o{ SESSAO_ESTUDO : alimenta
```

## 5. Tabela de Endpoints (API)
| Rota | Método | Descrição |
| :--- | :--- | :--- |
| `/api/auth/login` | POST | Autenticação do usuário |
| `/api/rag/ask` | POST | Busca vetorial e API retorna resposta LLM |
| `/api/gamification/xp` | POST | Adiciona pontos após conclusão de meta |
