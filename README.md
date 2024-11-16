# 아키텍쳐
```mermaid
flowchart TB
    subgraph Client["Client Side (Next.js)"]
        direction TB
        Pages["Pages (Next.js Pages)"]
        Components["Components"]
        Hooks["Custom Hooks"]
        
        subgraph State["State Management"]
            Zustand["Zustand Store"]
        end
        
        subgraph Styling["Styling Layer"]
            Emotion["Emotion/Styled Components"]
        end
    end

    subgraph Firebase["Firebase Services"]
        direction TB
        Auth["Firebase Authentication"]
        Firestore["Cloud Firestore"]
        Storage["Firebase Storage"]
        Analytics["Firebase Analytics"]
    end

    subgraph External["External Services"]
        KakaoMap["Kakao Map API"]
    end

    subgraph DevOps["DevOps & Deployment"]
        Git["Git Repository"]
        Husky["Husky (Git Hooks)"]
        Vercel["Vercel Deployment"]
    end

    %% Client-side connections
    Pages --> Components
    Components --> Hooks
    Components --> Emotion
    Components --> Zustand
    Hooks --> Zustand

    %% Firebase connections
    Components --> Auth
    Components --> Firestore
    Components --> Storage
    Components --> Analytics

    %% External API connection
    Components --> KakaoMap

    %% Deployment flow
    Git --> Husky
    Husky --> Vercel
    Vercel --> Client

    %% Styling
    style Client fill:#f9f,stroke:#333,stroke-width:2px
    style Firebase fill:#ffb,stroke:#333,stroke-width:2px
    style External fill:#bfb,stroke:#333,stroke-width:2px
    style DevOps fill:#bbf,stroke:#333,stroke-width:2px
  ```
