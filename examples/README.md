# Configuration Examples Analysis

## **Basic Configurations**

These examples are fairly basic and show you the YAML syntax for writing agents.

Some of these agents use [built-in tools](../docs/USAGE.md#tool-configuration)
like `filesystem`, which grants filesystem access, or `memory`, to allow the agent to store its findings for later use.

| Name                                   | Description/Purpose                    | Filesystem | Shell | Todo | Think | Memory | MCP Servers | Sub-agents |
|----------------------------------------|----------------------------------------|------------|-------|------|-------|--------|-------------|------------|
| [echo-agent.yaml](echo-agent.yaml)     | Simple echo agent                      |            |       |      |       |        |             |            |
| [pirate.yaml](pirate.yaml)             | Pirate-themed assistant                |            |       |      |       |        |             |            |
| [haiku.yaml](haiku.yaml)               | Writes Haikus                          |            |       |      |       |        |             |            |
| [42.yaml](42.yaml)                     | Douglas Adams-style witty AI assistant |            |       |      |       |        |             |            |
| [contradict.yaml](contradict.yaml)     | Contrarian viewpoint provider          |            |       |      |       |        |             |            |
| [silvia.yaml](silvia.yaml)             | Sylvia Plath-inspired poetic AI        |            |       |      |       |        |             |            |
| [script_shell.yaml](script_shell.yaml) | Agent with custom shell commands       |            | ✓     |      |       |        |             |            |
| [mem.yaml](mem.yaml)                   | Humorous AI with persistent memory     | ✓          |       |      |       | ✓      |             |            |
| [diag.yaml](diag.yaml)                 | Log analysis and diagnostics           | ✓          | ✓     |      | ✓     |        |             |            |
| [todo.yaml](todo.yaml)                 | Task manager example                   |            |       | ✓    |       |        |             |            |
| [pythonist.yaml](pythonist.yaml)       | Python programming assistant           | ✓          | ✓     |      |       |        |             |            |
| [alloy.yaml](alloy.yaml)               | Learning assistant                     |            |       |      |       |        |             |            |
| [dmr.yaml](dmr.yaml)                   | Pirate-themed AI assistant             |            |       |      |       |        |             |            |

## **Advanced Configurations**

These are more advanced examples, most of them involve some sort of MCP server to augment the agent capabilities with powerful custom integrations with third-party services.

| Name                                                   | Description/Purpose                         | Filesystem | Shell | Todo | Think | Memory | MCP Servers                                                                                                                    | Sub-agents |
|--------------------------------------------------------|---------------------------------------------|------------|-------|------|-------|--------|--------------------------------------------------------------------------------------------------------------------------------|------------|
| [bio.yaml](bio.yaml)                                   | Biography generation from internet searches |            |       |      |       |        | [duckduckgo](https://hub.docker.com/mcp/server/duckduckgo/overview), [fetch](https://hub.docker.com/mcp/server/fetch/overview) |            |
| [airbnb.yaml](airbnb.yaml)                             | Airbnb search specialist                    |            |       |      |       |        | `@openbnb/mcp-server-airbnb`                                                                                                   |            |
| [github_issue_manager.yaml](github_issue_manager.yaml) | GitHub Issue Manager                        |            |       |      |       |        | [github-official](https://hub.docker.com/mcp/server/github-official/overview)                                                  |            |
| [github.yaml](github.yaml)                             | Github assistance using MCP tools           |            |       |      |       |        | [github-official](https://hub.docker.com/mcp/server/github-official/overview)                                                  |            |
| [review.yaml](review.yaml)                             | Dockerfile review specialist                | ✓          |       |      |       |        |                                                                                                                                |            |
| [code.yaml](code.yaml)                                 | Code analysis and development assistant     | ✓          | ✓     | ✓    |       |        |                                                                                                                                |            |
| [go_packages.yml](go_packages.yml)                     | Golang packages expert                      |            |       |      |       |        |                                                                                                                                |            |
| [moby.yaml](moby.yaml)                                 | Moby Project Expert                         |            |       |      |       |        | `gitmcp.io/moby/moby`                                                                                                          |            |
| [image_text_extractor.yaml](image_text_extractor.yaml) | Image text extraction                       | ✓          |       |      |       |        |                                                                                                                                |            |
| [doc_generator.yaml](doc_generator.yaml)               | Documentation generation from codebases     |            | ✓     |      | ✓     |        |                                                                                                                                |            |
| [mcp_generator.yaml](mcp_generator.yaml)               | Generates MCP configurations                |            |       |      |       |        | docker,[duckduckgo](https://hub.docker.com/mcp/server/duckduckgo/overview)                                          |            |

## **Multi-Agent Configurations**

These examples are groups of agents working together. Each of them is specialized for a given task, and usually has some tools assigned to fulfill these tasks.
A coordinator agent usually makes them work together and checks that the work is finished.

| Name                                 | Description/Purpose                     | Filesystem | Shell | Todo | Think | Memory | MCP Servers                                                                    | Sub-agents |
|--------------------------------------|-----------------------------------------|------------|-------|------|-------|--------|--------------------------------------------------------------------------------|------------|
| [blog.yaml](blog.yaml)               | Technical blog writing workflow         |            |       |      | ✓     |        | [duckduckgo](https://hub.docker.com/mcp/server/duckduckgo/overview) | ✓          |
| [dev-team.yaml](dev-team.yaml)       | Development team coordinator            | ✓          | ✓     | ✓    | ✓     | ✓      |                                                                                | ✓          |
| [multi-code.yaml](multi-code.yaml)   | Technical lead and project coordination | ✓          | ✓     | ✓    | ✓     | ✓      |                                                                                | ✓          |
| [writer.yaml](writer.yaml)           | Story writing workflow supervisor       |            |       |      | ✓     |        |                                                                                | ✓          |
| [finance.yaml](finance.yaml)         | Financial research and analysis         |            |       |      | ✓     |        | [duckduckgo](https://hub.docker.com/mcp/server/duckduckgo/overview) | ✓          |
| [shared-todo.yaml](shared-todo.yaml) | Shared todo item manager                |            |       | ✓    |       |        |                                                                                | ✓          |
| [content_marketing_team.yaml](content_marketing_team.yaml) | Content marketing campaign team | ✓          |       |      | ✓     | ✓      |                                                                                | ✓          |
| [learning_tutor.yaml](learning_tutor.yaml)               | Adaptive learning and education tutor   | ✓          |       | ✓    | ✓     | ✓      |                                                                                |            |

## **New Agent Examples**

### Content Marketing Team (`content_marketing_team.yaml`)

A comprehensive multi-agent system for creating complete content marketing campaigns. This team demonstrates advanced collaboration patterns with specialized roles:

**Team Structure:**
- **Root (Team Lead)**: Coordinates strategy and execution, manages workflow
- **Content Strategist**: Develops data-driven content strategies and audience analysis
- **Copywriter**: Creates compelling content across multiple formats and platforms
- **SEO Specialist**: Optimizes content for search engines and performance tracking
- **Social Media Manager**: Adapts content for social platforms and engagement strategies

**Key Features:**
- Multiple AI models (Anthropic Claude for creativity, OpenAI GPT-4 for analysis)
- Shared memory database for campaign coordination
- Systematic workflow from strategy to execution
- Platform-specific content optimization
- Performance tracking and analytics guidance

**Use Cases:**
- Complete marketing campaign development
- Content strategy and planning
- SEO optimization and keyword research
- Social media content adaptation
- Brand messaging and voice development

### Learning Tutor (`learning_tutor.yaml`)

An adaptive educational agent that provides personalized learning experiences using cognitive science principles and evidence-based teaching methods.

**Core Capabilities:**
- **Learning Style Assessment**: Identifies and adapts to individual learning preferences
- **Personalized Curriculum**: Creates custom learning paths tailored to student needs
- **Interactive Teaching**: Uses Socratic questioning and hands-on activities
- **Progress Tracking**: Monitors advancement and adjusts strategies accordingly
- **Meta-Learning**: Teaches students how to learn effectively

**Teaching Framework:**
- ASSESS → PLAN → TEACH → PRACTICE → EVALUATE → ADAPT
- Multimodal learning support (visual, auditory, kinesthetic, reading/writing)
- Scaffolded learning with appropriate difficulty progression
- Growth mindset development and confidence building

**Subject Coverage:**
- STEM (Mathematics, Sciences, Computer Science, Engineering)
- Languages (English, Literature, Writing, Foreign Languages)
- Social Sciences (History, Psychology, Economics)
- Creative Arts (Art, Music, Creative Writing)
- Professional Skills (Business, Communication, Project Management)
- Life Skills (Study habits, Time management, Critical thinking)

**Use Cases:**
- Personalized tutoring across academic subjects
- Study skills and learning strategy development
- Adult education and professional development
- Homework assistance and concept reinforcement
- Learning disability support and accommodation
