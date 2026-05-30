# 🩺 DocFlow

## Sobre o Projeto
[cite_start]O DocFlow é uma plataforma web inovadora de agendamento e gestão de fluxo de pacientes para clínicas médicas[cite: 50]. [cite_start]O Produto Mínimo Viável (MVP) é focado estritamente na especialidade de Ginecologia e Obstetrícia (GO) para resolver complexidades reais, como a variação de tempo entre consultas e acompanhamentos de alto risco, além de bloqueios devido a plantões[cite: 51, 52]. [cite_start]O objetivo é promover disciplina operacional, permitindo um controle eficiente da agenda e a redução do tempo de espera[cite: 83].

## 🚀 Principais Funcionalidades
* [cite_start]**Tempos Dinâmicos de Serviço:** A duração da consulta se adapta automaticamente ao tipo de atendimento, sem a utilização de blocos de horários fixos engessados[cite: 65, 66].
* [cite_start]**Gestão de Status de Fluxo:** Utilização de uma esteira visual (Kanban) para acompanhar o paciente em tempo real: Agendado ➔ Confirmado ➔ Aguardando na Recepção ➔ Em Atendimento ➔ Finalizado / Faltou[cite: 67, 101].
* [cite_start]**Bloqueios de Agenda (Hard Blocks):** Recurso para o médico ou administrador bloquear horas, turnos ou dias inteiros de forma rápida, impedindo novos agendamentos[cite: 68, 103].
* [cite_start]**Prevenção de Conflitos (Anti Double-Booking):** Validação rigorosa no back-end e no banco de dados para garantir que dois pacientes não ocupem o mesmo horário com o mesmo médico[cite: 69, 104].
* [cite_start]**Autoagendamento Mobile:** Interface mobile-friendly para que o paciente visualize horários e solicite consultas de forma autônoma[cite: 62].

## 💻 Stack Tecnológica
* [cite_start]**Arquitetura:** Monorepo unificando Front-end e Back-end na mesma base de código[cite: 1].
* [cite_start]**Framework:** Next.js e React.js (App Router)[cite: 1, 105].
* [cite_start]**Linguagem:** TypeScript para tipagem estática e segurança do código[cite: 106].
* [cite_start]**Interface (UI):** Tailwind CSS e Shadcn UI[cite: 47, 107].
* [cite_start]**Banco de Dados:** PostgreSQL com Prisma ORM[cite: 48].
* [cite_start]**Segurança:** Autenticação via JWT com Role-Based Access Control (RBAC)[cite: 111].

## 📁 Estrutura de Diretórios

| Diretório | Propósito na Arquitetura |
| :--- | :--- |
| `prisma/` | [cite_start]Contém o arquivo schema.prisma para a modelagem do banco de dados relacional PostgreSQL e configurações do Prisma ORM[cite: 22]. |
| `src/app/(public)/` | [cite_start]Agrupa as rotas públicas do sistema, como a Landing Page e a tela de Login, que servirão como porta de entrada[cite: 23]. |
| `src/app/agendamento/` | [cite_start]Agrupa as telas do portal de autoagendamento, garantindo uma interface estritamente construída com foco mobile-first para o paciente[cite: 24]. |
| `src/app/panel/` | [cite_start]Funciona como o muro de segurança da aplicação, garantindo que tudo dentro desta rota exija autenticação validada (RBAC)[cite: 25]. |
| `src/app/panel/(medico)/` | [cite_start]Contém as rotas protegidas do dashboard de agenda diária e o visualizador de prontuários do corpo clínico[cite: 26]. |
| `src/app/panel/(recepcao)/` | [cite_start]Guarda as interfaces internas otimizadas para uso em Desktop, como a visão geral da recepção e a esteira visual de status (Kanban)[cite: 27]. |
| `src/app/api/` | [cite_start]Camada de Back-end responsável pelas chamadas ao banco de dados e regras de negócio, incluindo a validação rigorosa para prevenção de conflitos de agenda (double-booking)[cite: 28]. |
| `src/components/ui/` | [cite_start]Diretório base para os componentes visuais modernos, limpos e padronizados criados através da combinação de Tailwind CSS e Shadcn UI[cite: 29]. |
| `src/lib/` | [cite_start]Arquivos utilitários e lógicas compartilhadas, como a configuração da autenticação JWT e o controle de acesso baseado em funções[cite: 30]. |
| `src/types/` | [cite_start]Definições e interfaces de tipagem estática do TypeScript, garantindo um código mais seguro e a redução de bugs no sistema[cite: 31]. |

## 👥 Perfis de Acesso e Telas

* [cite_start]**Médico(a):** Possui acesso ao Dashboard de Agenda Diária, Painel de Acompanhamento de Fluxo, Visualizador de Prontuário e Gerenciador de Bloqueios[cite: 116, 117, 118, 119].
* [cite_start]**Recepção/Secretaria:** Acessa a Visão Geral da Recepção, Painel de Controle de Status (Kanban) e o Gestor de Encaixes e Remarcações de forma otimizada para Desktop[cite: 120, 121, 122].
* [cite_start]**Paciente:** Utiliza o Portal de Autoagendamento, a Tela de Solicitação de Consulta e recebe os dados na Tela de Confirmação[cite: 123, 124, 125].