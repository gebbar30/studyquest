graph TD
    A[Estudante EPT] -->|Acessa WebApp| B(Frontend - Next.js)
    B -->|Solicita Resumo/Dúvida| C{Backend API}
    
    subgraph Motor de IA (RAG Expandido)
        C -->|1. Busca Semântica| D[(Vector DB - Supabase)]
        C -->|Integração API| X[App/Plataforma da Instituição]
        D -.->|Retorna Contexto| C
        X -.->|Retorna Notas/Avisos| C
        C -->|2. Envia Contexto + Prompt| E[OpenAI API]
        E -->|3. Resposta Gerada| C
    end
    
    C -->|4. Exibe Resposta na Tela| B
    
    subgraph Gamificação
        C -.->|Registra XP / Streak| F[(Banco Relacional)]
    end

    erDiagram
    USUARIO {
        uuid id PK
        string nome
        string turno
        int xp_total
    }
    FONTE_DADOS {
        uuid id PK
        string tipo_fonte "PDF, App_Oficial, Plataforma_Web"
        string url_ou_arquivo
    }
    SESSAO_ESTUDO {
        uuid id PK
        uuid usuario_id FK
        int xp_ganho
    }
    USUARIO ||--o{ SESSAO_ESTUDO : "realiza"
    FONTE_DADOS ||--o{ SESSAO_ESTUDO : "alimenta a"
