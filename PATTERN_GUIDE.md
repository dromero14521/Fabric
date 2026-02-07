# Fabric Pattern Guide

This document provides a comprehensive overview of the available patterns in Fabric, what they do, and how to use them.

---

### `agility_story`

*   **Description**: An expert in the Agile framework that creates user stories and acceptance criteria.
*   **What it does**: Takes a topic as input and generates a user story and acceptance criteria for that topic.
*   **How to use it**:
    ```bash
    echo "Authentication and User Management" | fabric -p agility_story
    ```

---

### `ai`

*   **Description**: An expert at interpreting the heart and spirit of a question and answering in an insightful manner.
*   **What it does**: Deeply understands the input question, creates a mental model, and provides a concise answer in 3-5 markdown bullet points of 10 words each.
*   **How to use it**:
    ```bash
    echo "What is the meaning of life?" | fabric -p ai
    ```

---

### `analyze_answers`

*   **Description**: A PhD expert on the given subject that evaluates the correctness of provided answers.
*   **What it does**: Takes a subject, learning objectives, questions, and student answers as input. It then generates correct answers, evaluates the student's answers against them, provides a score, and a reasoning for the score.
*   **How to use it**:
    ```bash
    cat my_answers.txt | fabric -p analyze_answers
    ```
    Where `my_answers.txt` contains the subject, learning objectives, questions, and answers in the format specified in the pattern's `system.md` file.

---

### `analyze_bill`

*   **Description**: An AI with a 3,129 IQ that specializes in discerning the true nature and goals of a piece of legislation.
*   **What it does**: Reads a bill multiple times from different perspectives to identify both overt and covert goals. It provides metadata about the bill, a short summary, a list of overt and covert goals, and a concluding judgment.
*   **How to use it**:
    ```bash
    cat bill_text.txt | fabric -p analyze_bill
    ```

---

### `analyze_bill_short`

*   **Description**: An AI with a 3,129 IQ that specializes in discerning the true nature and goals of a piece of legislation, providing a shorter analysis.
*   **What it does**: Similar to `analyze_bill`, it reads a bill to identify overt and covert goals, but provides a more concise output. It gives bill metadata, a 16-word summary, a short list of overt and covert goals, and a 16-word conclusion.
*   **How to use it**:
    ```bash
---

### `analyze_candidates`

*   **Description**: An AI assistant that creates a pattern to analyze and compare two running candidates.
*   **What it does**: Examines each candidate's stances on key issues, highlights the pros and cons of their policies, and provides relevant background information to offer a comprehensive comparison.
*   **How to use it**:
    ```bash
    echo "Candidate A vs. Candidate B" | fabric -p analyze_candidates
    ```

---

### `analyze_cfp_submission`

*   **Description**: An AI assistant specialized in reviewing speaking session submissions for conferences.
*   **What it does**: Thoroughly analyzes and evaluates submission abstracts for quality, accuracy, educational value, and entertainment factor.
*   **How to use it**:
    ```bash
    cat submission.txt | fabric -p analyze_cfp_submission
    ```

---

### `analyze_claims`

*   **Description**: An objectively minded and centrist-oriented analyzer of truth claims and arguments.
*   **What it does**: Analyzes and rates the truth claims made in the input, providing evidence in support of those claims, as well as counter-arguments and counter-evidence.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p analyze_claims
    ```

---

### `analyze_comments`

*   **Description**: An expert at reading internet comments and characterizing their sentiments, praise, and criticisms.
*   **What it does**: Produces an unbiased and accurate assessment of the comments for a given piece of content, categorizing them as positive, negative, or neutral and providing reasons.
*   **How to use it**:
    ```bash
    cat comments.txt | fabric -p analyze_comments
    ```

---

### `analyze_debate`

*   **Description**: A neutral and objective entity to help humans understand debates to broaden their own views.
*   **What it does**: Consumes a debate transcript, analyzes the claims, and provides scores for insightfulness and emotionality, as well as lists of arguments, agreements, disagreements, and takeaways.
*   **How to use it**:
    ```bash
    cat debate_transcript.txt | fabric -p analyze_debate
    ```

---

### `analyze_email_headers`

*   **Description**: A cybersecurity and email expert that provides a detailed analysis of email headers.
*   **What it does**: Analyzes SPF, DKIM, DMARC, and ARC results from email headers, discusses security concerns, and provides actionable recommendations and `dig` commands for further investigation.
*   **How to use it**:
    ```bash
    cat email_headers.txt | fabric -p analyze_email_headers
    ```

---

### `analyze_incident`

*   **Description**: An AI that swiftly and effectively gathers essential information from articles about cybersecurity breaches.
*   **What it does**: Extracts key details from a cybersecurity breach article, including attack date, summary, attack type, vulnerable component, attacker and target information, and remediation steps.
*   **How to use it**:
    ```bash
    cat breach_article.txt | fabric -p analyze_incident
    ```

---

### `analyze_interviewer_techniques`

*   **Description**: A hyper-intelligent AI system that excels at extracting the special qualities of an interviewer's questions.
*   **What it does**: Analyzes a list of interview questions to identify the techniques being used and provides a summary of what makes the interviewer special.
*   **How to use it**:
    ```bash
    cat interview_questions.txt | fabric -p analyze_interviewer_techniques
    ```

---

### `analyze_logs`

*   **Description**: A system administrator and service reliability engineer with extensive experience in analyzing logs.
*   **What it does**: Analyzes a log file to identify patterns, anomalies, and potential issues, providing insights into the server's reliability and performance and recommending improvements.
*   **How to use it**:
    ```bash
    cat server.log | fabric -p analyze_logs
    ```

---

### `analyze_malware`

*   **Description**: A malware analysis expert for any platform.
*   **What it does**: Extracts indicators of compromise (IOCs), malware behavior, MITRE ATT&CK techniques, and other relevant information from a malware report. It also suggests a YARA rule for detection.
*   **How to use it**:
    ```bash
    cat malware_report.txt | fabric -p analyze_malware
    ```

---

### `analyze_military_strategy`

*   **Description**: A military historian and strategic analyst specializing in dissecting historical battles.
*   **What it does**: Provides a comprehensive analysis of a historical battle, including an overview, commanders, strategic decisions, strengths and weaknesses, pivotal moments, and logistical factors.
*   **How to use it**:
    ```bash
    echo "The Battle of Gettysburg" | fabric -p analyze_military_strategy
    ```

---

### `analyze_mistakes`

*   **Description**: An advanced AI expert in understanding and analyzing thinking patterns and the mistakes that arise from them.
*   **What it does**: Analyzes past mistaken thought patterns and applies that analysis to current beliefs or predictions to identify potential new errors and provide recommendations for adjustment.
*   **How to use it**:
    ```bash
    cat my_thoughts.txt | fabric -p analyze_mistakes
    ```

---

### `analyze_paper`

*   **Description**: A research paper analysis service focused on determining the primary findings and analyzing scientific rigor and quality.
*   **What it does**: Consumes a research paper and outputs a detailed analysis including a summary, authors, findings, study overview, and a quality rating with a final score.
*   **How to use it**:
    ```bash
    cat research_paper.txt | fabric -p analyze_paper
    ```

---

### `analyze_paper_simple`

*   **Description**: A research paper analysis service that provides a more concise analysis.
*   **What it does**: Consumes a research paper and outputs a simplified analysis including the title, a 16-word summary, implications, recommendation, authors, methodology, and potential conflicts of interest.
*   **How to use it**:
    ```bash
    cat research_paper.txt | fabric -p analyze_paper_simple
    ```

---

### `analyze_patent`

*   **Description**: A patent examiner with decades of experience.
*   **What it does**: Examines a patent's description and claims to identify the field, problem, solution, and advantage. It also assesses the novelty and inventive step of the patent.
*   **How to use it**:
    ```bash
    cat patent_text.txt | fabric -p analyze_patent
    ```

---

### `analyze_personality`

*   **Description**: A super-intelligent AI with full knowledge of human psychology and behavior.
*   **What it does**: Performs an in-depth psychological analysis on the main person in the input provided, giving an overview and supporting details.
*   **How to use it**:
    ```bash
    cat transcript.txt | fabric -p analyze_personality
    ```

---

### `analyze_presentation`

*   **Description**: An expert in reviewing and critiquing presentations.
*   **What it does**: Breaks down a presentation from both a content and presenter psychology perspective, providing scores for ideas, selflessness, and entertainment.
*   **How to use it**:
    ```bash
    cat presentation_transcript.txt | fabric -p analyze_presentation
    ```

---

### `analyze_product_feedback`

*   **Description**: An AI assistant specialized in analyzing user feedback for products.
*   **What it does**: Processes and organizes feedback, identifies themes, consolidates similar feedback, and prioritizes it based on usefulness, presenting the results in a table.
*   **How to use it**:
    ```bash
    cat feedback.csv | fabric -p analyze_product_feedback
    ```

---

### `analyze_proposition`

*   **Description**: An AI assistant that analyzes a federal, state, or local ballot proposition.
*   **What it does**: Meticulously examines a proposition to identify its purpose, potential impact, arguments for and against, and any relevant background information.
*   **How to use it**:
    ```bash
    cat proposition_text.txt | fabric -p analyze_proposition
    ```


---

### `analyze_prose_json`

*   **Description**: An expert writer and editor that evaluates the quality of writing and provides ratings and recommendations for improvement in JSON format.
*   **What it does**: Evaluates content for novelty, clarity, and prose, providing ratings, explanations, and recommendations in a structured JSON object.
*   **How to use it**:
    ```bash
    cat my_writing.txt | fabric -p analyze_prose_json
    ```

---

### `analyze_prose_pinker`

*   **Description**: An expert at assessing prose based on Steven Pinker's "The Sense of Style".
*   **What it does**: Analyzes prose to determine its writing style, provides a positive and critical assessment based on Pinker's principles, and offers recommendations for improvement.
*   **How to use it**:
    ```bash
    cat my_writing.txt | fabric -p analyze_prose_pinker
    ```

---

### `analyze_risk`

*   **Description**: A risk assessment specialist for third-party vendors.
*   **What it does**: Conducts a risk assessment of a vendor based on provided documents and their website, assigns a risk score (Low, Medium, or High), and provides a document explaining the reasoning and suggested security controls.
*   **How to use it**:
    ```bash
    cat vendor_documents.txt | fabric -p analyze_risk
    ```

---

### `analyze_sales_call`

*   **Description**: An advanced AI specializing in rating sales call transcripts.
*   **What it does**: Rates a sales call on sales fundamentals and pitch alignment with the company's vision, providing a summary, a list of failures, and recommendations for improvement.
*   **How to use it**:
    ```bash
    cat sales_call_transcript.txt | fabric -p analyze_sales_call
    ```

---

### `analyze_spiritual_text`

*   **Description**: An expert analyzer of spiritual texts.
*   **What it does**: Compares and contrasts the tenets and claims made within a spiritual text with the King James Bible, providing a list of surprising claims and differences with examples.
*   **How to use it**:
    ```bash
    cat spiritual_text.txt | fabric -p analyze_spiritual_text
    ```

---

### `analyze_tech_impact`

*   **Description**: A technology impact analysis service.
*   **What it does**: Determines the societal impact of technology projects by breaking down the project's intentions, outcomes, and broader implications for society, including ethical considerations.
*   **How to use it**:
    ```bash
    cat project_description.txt | fabric -p analyze_tech_impact
    ```

---

### `analyze_terraform_plan`

*   **Description**: An expert Terraform plan analyzer.
*   **What it does**: Takes a Terraform plan output and generates a Markdown formatted summary, focusing on assessing infrastructure changes, security risks, cost implications, and compliance considerations.
*   **How to use it**:
    ```bash
    terraform plan -out=plan.out && terraform show -json plan.out | fabric -p analyze_terraform_plan
    ```

---

### `analyze_threat_report`

*   **Description**: A super-intelligent cybersecurity expert specializing in extracting key information from cybersecurity threat reports.
*   **What it does**: Extracts surprising, insightful, and interesting trends, statistics, quotes, and recommendations from a cybersecurity threat report.
*   **How to use it**:
    ```bash
    cat threat_report.txt | fabric -p analyze_threat_report
    ```

---

### `analyze_threat_report_cmds`

*   **Description**: An AI that synthesizes information from a diverse panel of cybersecurity experts to provide actionable command-line input.
*   **What it does**: Extracts cybersecurity-related commands and specific command-line arguments from provided materials, incorporating perspectives from various experts.
*   **How to use it**:
    ```bash
    cat security_article.txt | fabric -p analyze_threat_report_cmds
    ```

---

### `analyze_threat_report_trends`

*   **Description**: A super-intelligent cybersecurity expert that extracts trends from cybersecurity threat reports.
*   **What it does**: Reads a threat report and extracts up to 50 of the most surprising, insightful, and/or interesting trends.
*   **How to use it**:
    ```bash
    cat threat_report.txt | fabric -p analyze_threat_report_trends
    ```

---

### `answer_interview_question`

*   **Description**: A versatile AI designed to help candidates excel in technical interviews.
*   **What it does**: Generates tailored, conversational responses to technical interview questions that reflect depth of knowledge and real-world experience.
*   **How to use it**:
    ```bash
    echo "Can you describe how you would manage project dependencies in a large software development project?" | fabric -p answer_interview_question
    ```

---

### `apply_ul_tags`

*   **Description**: A superintelligent expert on content of all forms, with deep understanding of which topics, categories, themes, and tags apply to any piece of content.
*   **What it does**: Applies a standardized set of tags to a piece of content and outputs them as a JSON object.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p apply_ul_tags
    ```

---

### `ask_secure_by_design_questions`

*   **Description**: An advanced AI specialized in securely building anything.
*   **What it does**: Takes an input and outputs a perfect set of "secure by design" questions to help the builder ensure the thing is created securely.
*   **How to use it**:
    ```bash
    echo "We are building a new online banking application." | fabric -p ask_secure_by_design_questions
    ```

---

### `ask_uncle_duke`

*   **Description**: An advanced AI system that coordinates multiple teams of AI agents to answer questions about software development.
*   **What it does**: Researches solutions from reputable sources, provides multiple options, and conducts code reviews based on user input.
*   **How to use it**:
    ```bash
    echo "[RESEARCH] How to implement JWT authentication in Spring Boot" | fabric -p ask_uncle_duke
    ```

---

### `audit_business_website`

*   **Description**: An expert Digital Audit Consultant and Conversion Rate Optimization (CRO) Specialist.
*   **What it does**: Analyzes a local business's website content or digital presence description to identify critical pain points, missing elements, and opportunities for improvement.
*   **How to use it**:
    ```bash
    curl -s "https://example.com" | fabric -p audit_business_website
    ```

---

### `automate_business_plan`

*   **Description**: An expert Chief Operating Officer (COO) and Lead Automation Architect.
*   **What it does**: Takes a high-level business plan and converts it into a "Business Automation Blueprint", including folder structures, workflow definitions, and starter code.
*   **How to use it**:
    ```bash
    cat business_plan.md | fabric -p automate_business_plan
    ```

---

### `automate_task`

*   **Description**: An expert DevOps Engineer and Scripting Automation Specialist.
*   **What it does**: Takes a natural language description of a task and generates a safe, efficient, and well-documented script (Bash or Python) to automate it.
*   **How to use it**:
    ```bash
    echo "Find all PDF files larger than 10MB in my Documents folder and zip them." | fabric -p automate_task
    ```

---

### `capture_thinkers_work`

*   **Description**: An AI that takes a philosopher, professional, or other notable thinker as input and outputs a template about what they taught.
*   **What it does**: Generates a detailed summary of a thinker's background, school of thought, most impactful ideas, primary advice, works, and quotes.
*   **How to use it**:
    ```bash
    echo "Socrates" | fabric -p capture_thinkers_work
    ```

---

### `check_agreement`

*   **Description**: An expert at analyzing contracts and agreements and looking for gotchas.
*   **What it does**: Takes a document and outputs a Markdown formatted summary, including a document summary, callouts of important aspects, and a list of critical, important, and other issues.
*   **How to use it**:
    ```bash
    cat agreement.txt | fabric -p check_agreement
    ```

---

### `clean_text`

*   **Description**: An expert at cleaning up broken and malformatted text.
*   **What it does**: Reads a document, removes strange line breaks, and adds capitalization, punctuation, and other formatting where necessary without changing the content.
*   **How to astyle="all: unset; color: inherit; cursor: text;">use it**:
    ```bash
    cat broken_text.txt | fabric -p clean_text
    ```

---

### `coding_master`

*   **Description**: An expert in understanding and digesting computer coding and computer languages.
*   **What it does**: Explains a coding concept as if teaching it to a beginner, using examples from reputable sources.
*   **How to use it**:
    ```bash
    echo "Explain the concept of recursion" | fabric -p coding_master
    ```

---

### `compare_and_contrast`

*   **Description**: An AI that compares and contrasts a list of items.
*   **What it does**: Takes a list of items as input and outputs a markdown table comparing and contrasting them on various topics.
*   **How to use it**:
    ```bash
    echo "Compare and contrast Python, Java, and Go" | fabric -p compare_and_contrast
    ```

---

### `convert_to_markdown`

*   **Description**: An expert format converter specializing in converting content to clean Markdown.
*   **What it does**: Preserves and converts the complete original post to markdown format, ensuring that all original formatting, links, and code blocks are preserved.
*   **How to use it**:
    ```bash
    cat content.html | fabric -p convert_to_markdown
    ```

---

### `create_5_sentence_summary`

*   **Description**: An all-knowing AI that creates concise summaries or answers at 5 different levels of depth.
*   **What it does**: Takes an input and provides summaries of 5 words, 4 words, 3 words, 2 words, and 1 word, reframing the meaning at each level.
*   **How to use it**:
    ```bash
    echo "Explain the theory of relativity" | fabric -p create_5_sentence_summary
    ```

---

### `create_academic_paper`

*   **Description**: An expert creator of LaTeX academic papers.
*   **What it does**: Takes an input and writes a high-quality academic paper in LaTeX formatting, laid out logically and simply while still looking authoritative.
*   **How to use it**:
    ```bash
    echo "My research on quantum computing" | fabric -p create_academic_paper
    ```

---

### `create_ai_jobs_analysis`

*   **Description**: An expert on AI and its effect on jobs.
*   **What it does**: Takes jobs reports and analysis and outputs a list of jobs that will be safer from automation, and provides recommendations on how to make yourself most safe.
*   **How to use it**:
    ```bash
    cat jobs_report.txt | fabric -p create_ai_jobs_analysis
    ```

---

### `create_aphorisms`

*   **Description**: An expert finder and printer of existing, known aphorisms.
*   **What it does**: Takes a topic as input and creates a list of 20 aphorisms from real people, including the person who said each one.
*   **How to use it**:
    ```bash
    echo "love and loss" | fabric -p create_aphorisms
    ```

---

### `create_art_prompt`

*   **Description**: An expert artist and AI whisperer who knows how to take a concept and give it to an AI to create the perfect piece of art.
*   **What it does**: Takes a concept and outputs a 100-word description of the concept and its visual representation, as well as direct instructions to the AI for how to create the art.
*   **How to use it**:
    ```bash
    echo "A city that runs on dreams" | fabric -p create_art_prompt
    ```

---

### `create_better_frame`

*   **Description**: An expert at finding better, positive mental frames for seeing the world.
*   **What it does**: Takes an input, looks for negative frames, and outputs a list of positive frames that could replace them.
*   **How to use it**:
    ```bash
    echo "I'm so bad at this, I'll never get it right." | fabric -p create_better_frame
    ```

---

### `create_coding_feature`

*   **Description**: An elite programmer that takes project ideas and outputs secure and composable code.
*   **What it does**: Takes a JSON file with a directory structure and instructions, and outputs a summary of file changes and a JSON array of file changes to be made.
*   **How to use it**:
    ```bash
    cat feature_request.json | fabric -p create_coding_feature
    ```

---

### `create_coding_project`

*   **Description**: An elite programmer that takes project ideas and outputs secure and composable code.
*   **What it does**: Takes a project idea and outputs a project summary, a step-by-step guide, a directory structure, a detailed explanation of each file, the code for each file, a setup script, takeaways, and suggestions.
*   **How to use it**:
    ```bash
    echo "A simple command-line chat application" | fabric -p create_coding_project
    ```

---

### `create_command`

*   **Description**: A penetration tester that is extremely good at reading and understanding command line help instructions.
*   **What it does**: Generates CLI commands for various tools that can be run to perform certain tasks based on the documentation given as input.
*   **How to use it**:
    ```bash
    cat tool_help.txt | fabric -p create_command
    ```
    Where `tool_help.txt` contains the help output of a command-line tool.

---

### `create_conceptmap`

*   **Description**: An intelligent assistant specialized in knowledge visualization and educational data structuring.
*   **What it does**: Reads unstructured text, extracts main concepts and relationships, and transforms them into a fully interactive conceptual map in a self-contained HTML file using Vis.js.
*   **How to use it**:
    ```bash
    cat my_notes.txt | fabric -p create_conceptmap > concept_map.html
    ```

---

### `create_cyber_summary`

*   **Description**: An expert in cybersecurity and writing summaries for busy technical people.
*   **What it does**: Creates a summary of all the different types of threats, vulnerabilities, stories, incidents, malware, and other newsworthy items from the input.
*   **How to use it**:
    ```bash
    cat security_news.txt | fabric -p create_cyber_summary
    ```

---

### `create_design_document`

*   **Description**: An expert in software, cloud, and cybersecurity architecture who specializes in creating clear, well-written design documents.
*   **What it does**: Takes a description of an idea or system and provides a detailed design document using the C4 model, including business and security posture, and mermaid diagrams for context, container, and deployment.
*   **How to use it**:
    ```bash
    echo "A new microservice for user authentication" | fabric -p create_design_document
    ```

---

### `create_diy`

*   **Description**: An AI assistant tasked with creating "Do It Yourself" tutorial patterns.
*   **What it does**: Analyzes a prompt to identify the requirements, materials, and ingredients for a tutorial, then organizes them into a structured format with comprehensive instructions.
*   **How to use it**:
    ```bash
    echo "How to build a birdhouse" | fabric -p create_diy
    ```

---

### `create_excalidraw_visualization`

*   **Description**: An expert AI that deeply understands the relationships between complex ideas and concepts and is an expert in the Excalidraw tool and schema.
*   **What it does**: Maps input concepts into Excalidraw diagram syntax so that humans can visualize the relationships between them.
*   **How to use it**:
    ```bash
    cat my_ideas.txt | fabric -p create_excalidraw_visualization > diagram.excalidraw
    ```

---

### `create_flash_cards`

*   **Description**: An expert educator AI that specializes in creating flashcards for key concepts.
*   **What it does**: Identifies key concepts, definitions, and terms from the input and creates flashcards for each with a question and an answer.
*   **How to use it**:
    ```bash
    cat study_notes.txt | fabric -p create_flash_cards
    ```

---

### `create_formal_email`

*   **Description**: An expert in formal communication with extensive knowledge in business etiquette and professional writing.
*   **What it does**: Assists in writing or responding to emails by understanding the context, purpose, and tone required, and generating a polished, concise, and appropriately formatted email.
*   **How to use it**:
    ```bash
    echo "Write an email to a professor asking for an extension on a paper." | fabric -p create_formal_email
    ```

---

### `create_git_diff_commit`

*   **Description**: An expert project manager and developer who specializes in creating super clean updates for what changed in a Git diff.
*   **What it does**: Reads a git diff and creates the git commands needed to add the changes to the repo, and a git commit message that reflects the changes using conventional commits.
*   **How to use it**:
    ```bash
    git diff | fabric -p create_git_diff_commit
    ```

---

### `create_graph_from_input`

*   **Description**: An expert at data visualization and information security.
*   **What it does**: Creates a progress-over-time graph in CSV format that shows how a security program is improving based on metrics and KPIs from the input.
*   **How to use it**:
    ```bash
    cat security_metrics.txt | fabric -p create_graph_from_input
    ```


---

### `create_idea_compass`

*   **Description**: A curious and organized thinker that aims to develop a structured and interconnected system of thoughts and ideas.
*   **What it does**: Takes an idea or question and explores its definition, evidence, source, similarities, opposites, theme, and consequences.
*   **How to use it**:
    ```bash
    echo "The concept of justice" | fabric -p create_idea_compass
    ```

---

### `create_investigation_visualization`

*   **Description**: An expert in intelligence investigations and data visualization using GraphViz.
*   **What it does**: Creates a full, detailed Graphviz visualization of the input, showing the most interesting, surprising, and useful aspects, including an analysis and conclusion.
*   **How to use it**:
    ```bash
    cat investigation_notes.txt | fabric -p create_investigation_visualization
    ```

---

### `create_keynote`

*   **Description**: An expert at creating TED-quality keynote presentations.
*   **What it does**: Takes input and creates a presentation with a narrative flow, including a title, main content, image description, and speaker notes for each slide.
*   **How to use it**:
    ```bash
    cat presentation_ideas.txt | fabric -p create_keynote
    ```

---

### `create_lead_guardian`

*   **Description**: An expert AI Architect and Sales Automation Strategist.
*   **What it does**: Designs a custom "Lead Guardian" AI agent for a specific local business, including the system prompt and implementation strategy.
*   **How to use it**:
    ```bash
    echo "I run a high-end dental clinic in Chicago." | fabric -p create_lead_guardian
    ```

---

### `create_loe_document`

*   **Description**: An expert in software, cloud, and cybersecurity architecture who specializes in creating clear, well-structured Level of Effort (LOE) documents.
*   **What it does**: Takes a description of a task or system and provides a detailed Level of Effort (LOE) document covering scope, business impact, resource requirements, estimated effort, risks, dependencies, and assumptions.
*   **How to use it**:
    ```bash
    echo "Migrate our monolithic application to a microservices architecture" | fabric -p create_loe_document
    ```

---

### `create_logo`

*   **Description**: An AI that creates simple, elegant, and impactful company logos.
*   **What it does**: Takes a company name or concept as input and outputs a prompt that can be sent to an AI image generator to create a simple, vector graphic logo.
*   **How to use it**:
    ```bash
    echo "A bookstore called 'The Reading Nook'" | fabric -p create_logo
    ```

---

### `create_markmap_visualization`

*   **Description**: An expert at data and concept visualization that turns complex ideas into a form that can be visualized using Markmap.
*   **What it does**: Takes input and creates a visualization that best explains it using proper Markmap syntax.
*   **How to use it**:
    ```bash
    cat my_notes.md | fabric -p create_markmap_visualization
    ```

---

### `create_mermaid_visualization`

*   **Description**: An expert at data and concept visualization that turns complex ideas into a form that can be visualized using Mermaid (markdown) syntax.
*   **What it does**: Takes input and creates a visualization that best explains it using elaborate and intricate Mermaid syntax.
*   **How to use it**:
    ```bash
    echo "A flowchart of our user authentication process" | fabric -p create_mermaid_visualization
    ```

---

### `create_mermaid_visualization_for_github`

*   **Description**: An expert at data and concept visualization that turns complex ideas into a form that can be visualized using Mermaid (markdown) syntax for GitHub.
*   **What it does**: Takes input and creates a visualization that best explains it using elaborate and intricate Mermaid syntax, formatted for display on GitHub.
*   **How to use it**:
    ```bash
    echo "A sequence diagram of our API call" | fabric -p create_mermaid_visualization_for_github
    ```

---

### `create_micro_summary`

*   **Description**: An expert content summarizer.
*   **What it does**: Takes content and outputs a Markdown formatted summary including a 20-word one-sentence summary, 3 main points, and 3 takeaways.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p create_micro_summary
    ```

---

### `create_monetization_plan`

*   **Description**: An expert AI Business Model Architect and Agency Scaler.
*   **What it does**: Analyzes your specific assets (LLC, VPS, APIs, Patterns) to generate a comprehensive business monetization roadmap.
*   **How to use it**:
    ```bash
    echo "I have an LLC, a VPS, and these APIs..." | fabric -p create_monetization_plan
    ```

---

### `create_mnemonic_phrases`

*   **Description**: A creative language assistant responsible for creating memorable mnemonic bridges in the form of sentences from given words.
*   **What it does**: Takes a list of words and creates five short, memorable sentences, with each sentence containing all the given words in the exact same order.
*   **How to use it**:
    ```bash
    echo "King Phillip Came Over For Good Soup" | fabric -p create_mnemonic_phrases
    ```

---

### `create_network_threat_landscape`

*   **Description**: A network security consultant that analyzes open ports and services.
*   **What it does**: Takes two bulleted lists of network port and service statistics and creates a markdown formatted threat report with a description, risk analysis, recommendations, and trends.
*   **How to use it**:
    ```bash
    cat port_scan_results.txt | fabric -p create_network_threat_landscape
    ```

---

### `create_newsletter_entry`

*   **Description**: A custom GPT designed to create newsletter sections in the style of Frontend Weekly.
*   **What it does**: Condenses an article into one summarizing newsletter entry of less than 70 words and generates a concise title for the entry.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p create_newsletter_entry
    ```

---

### `create_npc`

*   **Description**: An expert NPC generator for D&D 5th edition.
*   **What it does**: Creates a D&D 5E NPC with a detailed background, character flaws, attributes, stats, past experiences, goals, and more.
*   **How to use it**:
    ```bash
    echo "A grumpy blacksmith with a heart of gold" | fabric -p create_npc
    ```

---

### `create_pattern`

*   **Description**: An AI assistant that interprets LLM/AI prompts and delivers responses based on pre-defined structures.
*   **What it does**: Analyzes a prompt to identify the specific instructions and any provided examples, then generates an output that precisely matches the requested structure.
*   **How to use it**:
    ```bash
    cat prompt.txt | fabric -p create_pattern
    ```

---

### `create_prd`

*   **Description**: A Product Requirements Document (PRD) Generator.
*   **What it does**: Transforms product ideas, prompts, or descriptions into a structured PRD, outlining the product’s goals, features, technical requirements, and user experience considerations.
*   **How to use it**:
    ```bash
    echo "A mobile app that helps users find local hiking trails" | fabric -p create_prd
    ```

---

### `create_prediction_block`

*   **Description**: A hyper-intelligent AI system that creates blocks of markdown for predictions made in a particular piece of input.
*   **What it does**: Extracts predictions from content and formats them into a structured markdown block with the prediction, date, quote, references, status, and notes.
*   **How to use it**:
    ```bash
    cat article_with_predictions.txt | fabric -p create_prediction_block
    ```

---

### `create_quiz`

*   **Description**: An expert on the given subject that generates review questions for a student.
*   **What it does**: Takes a subject and learning objectives and generates up to three challenging review questions for each objective, adapted to the specified student level.
*   **How to use it**:
    ```bash
    cat course_material.txt | fabric -p create_quiz
    ```

---

### `create_reading_plan`

*   **Description**: An AI that designs a perfect three-phase reading plan.
*   **What it does**: Takes guidance and/or an author name as input and creates a three-phase reading plan (core, extended, and exploratory) to help the user become knowledgeable about the author or topic.
*   **How to use it**:
    ```bash
    echo "I want to learn about the works of Fyodor Dostoevsky" | fabric -p create_reading_plan
    ```

---

### `create_recursive_outline`

*   **Description**: An AI assistant specialized in task decomposition and recursive outlining.
*   **What it does**: Takes complex tasks, projects, or ideas and breaks them down into smaller, more manageable components in a hierarchical outline.
*   **How to use it**:
    ```bash
    echo "Write a book about the history of the internet" | fabric -p create_recursive_outline
    ```

---

### `create_rpg_summary`

*   **Description**: An expert summarizer of in-person role-playing game sessions.
*   **What it does**: Takes an RPG transcript and turns it into a useful summary of the session, including key events, combat stats, character flaws, and more.
*   **How to use it**:
    ```bash
    cat rpg_transcript.txt | fabric -p create_rpg_summary
    ```

---

### `create_security_update`

*   **Description**: An expert at creating concise security updates for newsletters.
*   **What it does**: Takes security news and creates a summary of threats, advisories, and vulnerabilities.
*   **How to use it**:
    ```bash
    cat security_articles.txt | fabric -p create_security_update
    ```

---

### `create_show_intro`

*   **Description**: An expert podcast and media producer specializing in creating compelling short intros.
*   **What it does**: Takes a show transcript and creates a short intro that lists the topics discussed.
*   **How to use it**:
    ```bash
    cat show_transcript.txt | fabric -p create_show_intro
    ```

---

### `create_sigma_rules`

*   **Description**: An expert cybersecurity detection engineer for a SIEM company.
*   **What it does**: Takes security news publications and extracts Tactics, Techniques, and Procedures (TTPs), then translates them into YAML-based Sigma rules.
*   **How to use it**:
    ```bash
    cat security_article.txt | fabric -p create_sigma_rules
    ```

---

### `create_story_about_people_interaction`

*   **Description**: An AI that constructs a comprehensive psychological profile for two individuals and writes a fictional narrative about their interaction.
*   **What it does**: Analyzes the input for each person, compares and contrasts their profiles, and writes a story that reflects the most probable and psychologically realistic outcomes of their meeting.
*   **How to use it**:
    ```bash
    cat profiles.txt | fabric -p create_story_about_people_interaction
    ```

---

### `create_story_about_person`

*   **Description**: An expert creative writer specializing in character-driven narratives.
*   **What it does**: Crafts a compelling, realistic short story based on a psychological profile or personal data provided by the user.
*   **How to use it**:
    ```bash
    cat character_profile.txt | fabric -p create_story_about_person
    ```

---

### `create_story_explanation`

*   **Description**: An AI that excels at understanding complex content and explaining it in a conversational, story-like format.
*   **What it does**: Transforms the provided content into a clear, approachable summary that walks readers through the key concepts in a flowing narrative style.
*   **How to use it**:
    ```bash
    cat complex_topic.txt | fabric -p create_story_explanation
    ```

---

### `create_stride_threat_model`

*   **Description**: An expert in risk and threat management and cybersecurity.
*   **What it does**: Creates a threat model using the STRIDE per element methodology for any system, based on a provided design document.
*   **How to use it**:
    ```bash
    cat design_document.txt | fabric -p create_stride_threat_model
    ```

---

### `create_summary`

*   **Description**: An expert content summarizer.
*   **What it does**: Takes content and outputs a Markdown formatted summary including a 20-word one-sentence summary, 10 main points, and 5 takeaways.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p create_summary
    ```

---

### `create_tags`

*   **Description**: An AI that identifies tags from text content for mind mapping tools.
*   **What it does**: Carefully considers the topics and content of the text and identifies at least 5 subjects/ideas to be used as tags.
*   **How to use it**:
    ```bash
    cat my_document.txt | fabric -p create_tags
    ```

---

### `create_threat_scenarios`

*   **Description**: An expert in risk and threat management and cybersecurity.
*   **What it does**: Creates simple, narrative-based threat models for all types of scenarios, from physical security concerns to cybersecurity analysis.
*   **How to use it**:
    ```bash
    echo "Threat model for my home network" | fabric -p create_threat_scenarios
    ```

---

### `create_ttrc_graph`

*   **Description**: An expert at data visualization and information security.
*   **What it does**: Creates a progress-over-time graph in CSV format for the Time to Remediate Critical Vulnerabilities metric.
*   **How to use it**:
    ```bash
    cat vulnerability_data.txt | fabric -p create_ttrc_graph
    ```

---

### `create_ttrc_narrative`

*   **Description**: An expert at data visualization and information security.
*   **What it does**: Creates a compelling and professional narrative that shows a program is making great progress in reducing the time to remediate critical vulnerabilities.
*   **How to use it**:
    ```bash
    cat vulnerability_data.txt | fabric -p create_ttrc_narrative
    ```

---

### `create_upgrade_pack`

*   **Description**: An expert at extracting world model and task algorithm updates from input.
*   **What it does**: Extracts world model beliefs and task algorithm ideas from content and presents them as a list of updates.
*   **How to use it**:
    ```bash
    cat book_summary.txt | fabric -p create_upgrade_pack
    ```

---

### `create_user_story`

*   **Description**: An expert on writing concise, clear, and illuminating technical user stories for new features in complex software programs.
*   **What it does**: Writes a user story with a description and acceptance criteria in a fashion recognized by other software stakeholders.
*   **How to use it**:
    ```bash
    echo "As a user, I want to be able to reset my password." | fabric -p create_user_story
    ```

---

### `create_video_chapters`

*   **Description**: An expert conversation topic and timestamp creator.
*   **What it does**: Takes a transcript and extracts the most interesting topics discussed, providing timestamps for where in the video they occur.
*   **How to use it**:
    ```bash
    cat video_transcript.txt | fabric -p create_video_chapters
    ```

---

### `create_visualization`

*   **Description**: An expert at data and concept visualization that turns complex ideas into a form that can be visualized using ASCII art.
*   **What it does**: Takes input and creates a visualization that best explains it using elaborate and intricate ASCII art.
*   **How to use it**:
    ```bash
    echo "The water cycle" | fabric -p create_visualization
    ```

---

### `dialog_with_socrates`

*   **Description**: A modern-day philosopher named Socrates who desires to engage in deep, meaningful conversations.
*   **What it does**: Guides an interlocutor to answers with thought-provoking questions, fostering independent, critical thinking (the Socratic Method).
*   **How to use it**:
    ```bash
    echo "What is justice?" | fabric -p dialog_with_socrates
    ```

---

### `enrich_blog_post`

*   **Description**: A hyper-intelligent AI system that excels at enriching Markdown blog files.
*   **What it does**: Takes a Markdown blog file and enhances its structure, visuals, and other aspects of quality by following a set of instructions.
*   **How to use it**:
    ```bash
    cat blog_post.md | fabric -p enrich_blog_post
    ```

---

### `explain_docs`

*   **Description**: An expert at capturing, understanding, and explaining the most important parts of instructions or documentation.
*   **What it does**: Takes tool documentation as input and outputs a structured explanation including an overview, common syntax, use cases, and important options.
*   **How to use it**:
    ```bash
    cat tool_documentation.txt | fabric -p explain_docs
    ```

---

### `explain_math`

*   **Description**: A math teacher that explains mathematical equations or concepts in easy-to-understand terms.
*   **What it does**: Provides step-by-step instructions for solving a problem, demonstrates various techniques, and suggests online resources for further study.
*   **How to use it**:
    ```bash
    echo "Explain the Pythagorean theorem" | fabric -p explain_math
    ```

---

### `explain_project`

*   **Description**: An expert at explaining projects and how to use them.
*   **What it does**: Takes project documentation and outputs a crisp, user and developer-focused summary of what the project does and how to use it.
*   **How to use it**:
    ```bash
    cat project_readme.md | fabric -p explain_project
    ```

---

### `explain_terms`

*   **Description**: The world's best explainer of terms required to understand a given piece of content.
*   **What it does**: Takes input and produces a glossary of important terms mentioned, including a definition, analogy, and why the term matters.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p explain_terms
    ```

---

### `export_data_as_csv`

*   **Description**: A superintelligent AI that finds all mentions of data structures within an input and outputs properly formatted CSV data.
*   **What it does**: Finds all data structures in the input and outputs a CSV file that contains the data.
*   **How to use it**:
    ```bash
    cat data.json | fabric -p export_data_as_csv
    ```

---

### `extract_algorithm_update_recommendations`

*   **Description**: An expert interpreter of the algorithms described for doing things within content.
*   **What it does**: Extracts concise, practical recommendations for how to do something from the input and outputs them as a bulleted list.
*   **How to use it**:
    ```bash
    cat article_on_best_practices.txt | fabric -p extract_algorithm_update_recommendations
    ```

---

### `extract_alpha`

*   **Description**: An expert at finding "Alpha" (novel and surprising ideas) in content.
*   **What it does**: Extracts the 24 highest alpha ideas, thoughts, insights, and recommendations from a piece of content and outputs them as 8-word bullets.
*   **How to use it**:
    ```bash
    cat transcript.txt | fabric -p extract_alpha
    ```

---

### `extract_article_wisdom`

*   **Description**: An AI that extracts surprising, insightful, and interesting information from text content.
*   **What it does**: Extracts a summary, ideas, quotes, facts, references, and recommendations from the input content.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p extract_article_wisdom
    ```

---

### `extract_book_ideas`

*   **Description**: An AI that takes a book name as input and outputs a full summary of the book's most important ideas.
*   **What it does**: Extracts 50 to 100 of the most surprising, insightful, and/or interesting ideas from the book.
*   **How to use it**:
    ```bash
    echo "Sapiens: A Brief History of Humankind" | fabric -p extract_book_ideas
    ```

---

### `extract_book_recommendations`

*   **Description**: An AI that takes a book name as input and outputs a full summary of the book's most important recommendations.
*   **What it does**: Extracts 50 to 100 of the most practical recommendations from the book.
*   **How to use it**:
    ```bash
    echo "The 7 Habits of Highly Effective People" | fabric -p extract_book_recommendations
    ```

---

### `extract_business_ideas`

*   **Description**: A business idea extraction assistant.
*   **What it does**: Extracts all the top business ideas from the content and then elaborates on the best 10 ideas by pivoting into an adjacent idea.
*   **How to use it**:
    ```bash
    cat business_article.txt | fabric -p extract_business_ideas
    ```

---

### `extract_characters`

*   **Description**: An advanced information-extraction analyst that specializes in reading any text and identifying its characters.
*   **What it does**: Extracts a deduplicated list of characters, resolves aliases/pronouns, and explains each character’s role and interactions in the narrative.
*   **How to use it**:
    ```bash
    cat story.txt | fabric -p extract_characters
    ```

---

### `extract_controversial_ideas`

*   **Description**: A super-intelligent AI system that extracts the most controversial statements out of inputs.
*   **What it does**: Creates a full list of controversial statements from the input, including a list of controversial ideas and supporting quotes.
*   **How to use it**:
    ```bash
    cat debate_transcript.txt | fabric -p extract_controversial_ideas
    ```

---

### `extract_core_message`

*   **Description**: An expert at looking at a presentation, an essay, or a full body of lifetime work, and clearly and accurately articulating what the core message is.
*   **What it does**: Produces a single, 15-word sentence that perfectly articulates the core message as presented in the input.
*   **How to use it**:
    ```bash
    echo "The works of Marcus Aurelius" | fabric -p extract_core_message
    ```

---

### `extract_ctf_writeup`

*   **Description**: A seasoned cyber security veteran who explains complex technical attacks in a way that people unfamiliar with it can learn.
*   **What it does**: Extracts a management summary, a list of vulnerabilities, a timeline of the attack, and a list of references from a CTF writeup or war story.
*   **How to use it**:
    ```bash
    cat ctf_writeup.txt | fabric -p extract_ctf_writeup
    ```

---

### `extract_domains`

*   **Description**: An AI that extracts domains and URLs from input for the purpose of understanding the sources that were used for their content.
*   **What it does**: For every story mentioned in the input, it outputs the central source (not necessarily the exact URL).
*   **How to use it**:
    ```bash
    cat newsletter.txt | fabric -p extract_domains
    ```

---

### `extract_extraordinary_claims`

*   **Description**: An expert at extracting extraordinary claims from conversations.
*   **What it does**: Identifies and extracts claims that are already accepted as false by the scientific community, not easily verifiable, or generally understood to be false by the consensus of experts.
*   **How to use it**:
    ```bash
    cat conspiracy_theory_video_transcript.txt | fabric -p extract_extraordinary_claims
    ```

---

### `extract_ideas`

*   **Description**: An advanced AI with a 2,128 IQ that is an expert in understanding any input and extracting the most important ideas from it.
*   **What it does**: Extracts all of the ideas from the content in 15-word bullet points.
*   **How to use it**:
    ```bash
    cat book_summary.txt | fabric -p extract_ideas
    ```

---

### `extract_insights`

*   **Description**: An expert at extracting the most surprising, powerful, and interesting insights from content.
*   **What it does**: Extracts 10 of the most surprising and novel insights from the input and outputs them as 8-word bullets.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p extract_insights
    ```

---

### `extract_instructions`

*   **Description**: An expert at extracting clear, concise step-by-step instructions from instructional video transcripts.
*   **What it does**: Extracts and presents key instructions from a given transcript in an easy-to-follow format, including objectives and numbered steps.
*   **How to use it**:
    ```bash
    cat video_transcript.txt | fabric -p extract_instructions
    ```

---

### `extract_jokes`

*   **Description**: An AI that extracts jokes from text content.
*   **What it does**: Extracts jokes from text content and presents each joke with its punchline in bullet points.
*   **How to use it**:
    ```bash
    cat humorous_text.txt | fabric -p extract_jokes
    ```

---

### `extract_latest_video`

*   **Description**: An expert at extracting the latest video URL from a YouTube RSS feed.
*   **What it does**: Reads a YouTube RSS feed, finds the latest posted video URL, and outputs the full video URL.
*   **How to use it**:
    ```bash
    cat youtube_rss_feed.xml | fabric -p extract_latest_video
    ```

---

### `extract_main_activities`

*   **Description**: An expert activity extracting AI that specializes in taking any transcript and extracting the key events that happened.
*   **What it does**: Extracts key events and shared contexts from a transcript or log, provides a summary sentence, and lists the main events.
*   **How to use it**:
    ```bash
    cat log_file.txt | fabric -p extract_main_activities
    ```

---

### `extract_main_idea`

*   **Description**: An AI that extracts the primary and/or most surprising, insightful, and interesting idea from any input.
*   **What it does**: Extracts the most important idea and the main recommendation from the content in 15-word sentences.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p extract_main_idea
    ```

---

### `extract_mcp_servers`

*   **Description**: An expert at analyzing content related to MCP (Model Context Protocol) servers.
*   **What it does**: Identifies and extracts mentions of MCP servers, their features, capabilities, integrations, and usage patterns, presenting a summary and details.
*   **How to use it**:
    ```bash
    cat mcp_documentation.txt | fabric -p extract_mcp_servers
    ```

---

### `extract_most_redeeming_thing`

*   **Description**: An expert at looking at an input and extracting the most redeeming thing about it.
*   **What it does**: Produces a single, 15-word sentence that perfectly articulates the most redeeming thing with the world as presented in the input.
*   **How to use it**:
    ```bash
    cat content.txt | fabric -p extract_most_redeeming_thing
    ```

---

### `extract_patterns`

*   **Description**: An AI that takes a collection of ideas or data or observations and looks for the most interesting and surprising patterns.
*   **What it does**: Extracts 20 to 50 patterns, provides meta-analysis of the assembly process, gives a one-sentence summary, lists the best 5 patterns, and offers advice for builders.
*   **How to use it**:
    ```bash
    cat observations.txt | fabric -p extract_patterns
    ```

---

### `extract_poc`

*   **Description**: A super powerful AI cybersecurity expert system specialized in finding and extracting proof of concept URLs.
*   **What it does**: Extracts the proof of concept URL and the command to run it from submitted security/bug bounty reports.
*   **How to use it**:
    ```bash
    cat bug_bounty_report.txt | fabric -p extract_poc
    ```

---

### `extract_predictions`

*   **Description**: An AI that fully digests input and extracts the predictions made within.
*   **What it does**: Extracts predictions, including the specific prediction, date, confidence level, and how to verify, and presents them in a bulleted list and a table.
*   **How to use it**:
    ```bash
    cat article_with_predictions.txt | fabric -p extract_predictions
    ```

---

### `extract_primary_problem`

*   **Description**: An expert at clearly and accurately articulating what the author(s) believe is the primary problem with the world.
*   **What it does**: Produces a single, 15-word sentence that perfectly articulates the primary problem with the world as presented in a given text or body of work.
*   **How to use it**:
    ```bash
    echo "The philosophy of Jean-Jacques Rousseau" | fabric -p extract_primary_problem
    ```

---

### `extract_primary_solution`

*   **Description**: An expert at clearly and accurately articulating what the author(s) believe is the primary solution for the world.
*   **What it does**: Produces a single, 15-word sentence that perfectly articulates the primary solution for the world as presented in a given text or body of work.
*   **How to use it**:
    ```bash
    echo "The philosophy of Karl Marx" | fabric -p extract_primary_solution
    ```

---

### `extract_product_features`

*   **Description**: An AI that extracts the list of product features from the input.
*   **What it does**: Consumes content about a product announcement or service and outputs a bulleted list of its features.
*   **How to use it**:
    ```bash
    cat product_announcement.txt | fabric -p extract_product_features
    ```

---

### `extract_questions`

*   **Description**: An advanced AI with a 419 IQ that excels at extracting all of the questions asked by an interviewer within a conversation.
*   **What it does**: Extracts all the questions asked by an interviewer from a conversation transcript and lists them as a series of bullet points.
*   **How to use it**:
    ```bash
    cat interview_transcript.txt | fabric -p extract_questions
    ```

---

### `extract_recipe`

*   **Description**: A passionate chef who loves to cook different food from different countries and continents.
*   **What it does**: Extracts a short description of a meal, a list of ingredients with measurements, and step-by-step instructions to prepare the meal.
*   **How to use it**:
    ```bash
    cat recipe_article.txt | fabric -p extract_recipe
    ```

---

### `extract_recommendations`

*   **Description**: An expert interpreter of the recommendations present within a piece of content.
*   **What it does**: Extracts concise, practical recommendations that are either explicitly made in the content or naturally flow from it.
*   **How to use it**:
    ```bash
    cat business_report.txt | fabric -p extract_recommendations
    ```

---

### `extract_references`

*   **Description**: An expert extractor of references to art, stories, books, literature, papers, and other sources of learning from content.
*   **What it does**: Extracts all references to art, stories, books, literature, papers, and other sources of learning into a bulleted list.
*   **How to use it**:
    ```bash
    cat academic_paper.txt | fabric -p extract_references
    ```

---

### `extract_skills`

*   **Description**: An expert in extracting skill terms from a job description and classifying them.
*   **What it does**: Extracts all the skills from a job description and reports them in a table with two columns: "skill name" and "skill type" (hard or soft).
*   **How to use it**:
    ```bash
    cat job_description.txt | fabric -p extract_skills
    ```

---

### `extract_song_meaning`

*   **Description**: An expert songwriter and musician that specializes in understanding the meaning of songs.
*   **What it does**: Takes any input about a song and outputs a summary sentence, a longer description of its meaning, and evidence to support the interpretation.
*   **How to use it**:
    ```bash
    echo "Analyze the song 'Bohemian Rhapsody' by Queen" | fabric -p extract_song_meaning
    ```

---

### `extract_videoid`

*   **Description**: An expert at extracting video IDs from any URL.
*   **What it does**: Takes a URL, finds the portion that identifies the video ID, and outputs just that video ID.
*   **How to use it**:
    ```bash
    echo "https://www.youtube.com/watch?v=dQw4w9WgXcQ" | fabric -p extract_videoid
    ```

---

### `extract_wisdom`

*   **Description**: An AI that extracts surprising, insightful, and interesting information from text content.
*   **What it does**: Extracts a summary, ideas, quotes, habits, facts, references, and recommendations related to human flourishing, AI, learning, and similar topics.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p extract_wisdom
    ```

---

### `extract_wisdom_agents`

*   **Description**: An advanced AI system that coordinates multiple teams of AI agents to extract surprising, insightful, and interesting information from text content.
*   **What it does**: Uses a team of AI agents with different perspectives to extract a summary, ideas, insights, quotes, habits, facts, references, and recommendations from the input.
*   **How to use it**:
    ```bash
    cat book_chapter.txt | fabric -p extract_wisdom_agents
    ```

---

### `extract_wisdom_dm`

*   **Description**: A hyper-intelligent AI system that excels at extracting interesting, novel, surprising, insightful, and otherwise thought-provoking information from input.
*   **What it does**: Produces a perfect extraction of all valuable content from the input, focusing on topics like purpose, meaning, AI, and human flourishing, similar to `extract_insights_dm` but with slightly different output instructions.
*   **How to use it**:
    ```bash
    cat podcast_transcript.txt | fabric -p extract_wisdom_dm
    ```

---

### `extract_wisdom_nometa`

*   **Description**: An AI that extracts surprising, insightful, and interesting information from text content, similar to `extract_wisdom` but without metadata.
*   **What it does**: Extracts a summary, ideas, quotes, habits, facts, references, and recommendations related to human flourishing, AI, learning, and similar topics, but with specific formatting for output.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p extract_wisdom_nometa
    ```

---

### `find_female_life_partner`

*   **Description**: A relationship, marriage, and life happiness expert AI.
*   **What it does**: Takes criteria about what a man is looking for in a woman life partner and turns it into clear, direct, and poetic sentences that answer "What would I tell people I'm looking for if I knew what I wanted and wasn't afraid."
*   **How to use it**:
    ```bash
    echo "I want someone who is intelligent, kind, and loves adventure." | fabric -p find_female_life_partner
    ```

---

### `find_hidden_message`

*   **Description**: An expert in political propaganda, analysis of hidden messages, and political narrative creation.
*   **What it does**: Consumes input and cynically evaluates what's being said to find the overt versus hidden political messages, supporting arguments, desired audience actions, and a cynical analysis.
*   **How to use it**:
    ```bash
    cat political_speech.txt | fabric -p find_hidden_message
    ```

---

### `find_logical_fallacies`

*   **Description**: An expert on all the different types of fallacies that are often used in argument and identifying them in input.
*   **What it does**: Reads an input text, identifies all instances of logical fallacies, and lists them with their type and a brief explanation.
*   **How to use it**:
    ```bash
    cat argument.txt | fabric -p find_logical_fallacies
    ```

---

### `fix_typos`

*   **Description**: An AI assistant designed to function as a proofreader and editor.
*   **What it does**: Meticulously analyzes text to identify and correct all typographical errors, including spelling, grammatical errors, punctuation issues, and other typos.
*   **How to use it**:
    ```bash
    cat document_with_typos.txt | fabric -p fix_typos
    ```

---

### `generate_code_rules`

*   **Description**: A senior developer and expert prompt engineer.
*   **What it does**: Distills a transcription or tutorial into a set of unique rules for best practices guidance in AI-assisted coding tools.
*   **How to use it**:
    ```bash
    cat coding_tutorial.txt | fabric -p generate_code_rules
    ```

---

### `get_wow_per_minute`

*   **Description**: An expert at determining the wow-factor of content as measured per minute.
*   **What it does**: Measures the density of "wow-factor" (surprise, novelty, insight, value, and wisdom) in content and outputs a JSON object with scores and explanations.
*   **How to use it**:
    ```bash
    cat video_transcript.txt | fabric -p get_wow_per_minute
    ```

---

### `greybeard_secure_prompt_engineer`

*   **Description**: Greybeard, a principal-level systems engineer and security reviewer with NASA-style mission assurance discipline.
*   **What it does**: Produces secure, reliable, auditable system prompts and companion scaffolding from vague or unsafe prompting.
*   **How to use it**:
    ```bash
    cat prompt_draft.txt | fabric -p greybeard_secure_prompt_engineer
    ```

---

### `heal_person`

*   **Description**: An AI assistant whose primary responsibility is to interpret and analyze psychological profiles and/or psychology data files.
*   **What it does**: Develops a tailored plan aimed at spiritual and mental healing, as well as overall life improvement for the subject.
*   **How to use it**:
    ```bash
    cat psychological_profile.txt | fabric -p heal_person
    ```

---

### `humanize`

*   **Description**: A real person whose job is to make text sound natural, conversational, and relatable.
*   **What it does**: Rewrites AI-generated text to sound like it was written by a real person, prioritizing clarity, simplicity, and natural tone while preserving the original meaning.
*   **How to use it**:
    ```bash
    cat ai_generated_text.txt | fabric -p humanize
    ```

---

### `identify_dsrp_distinctions`

*   **Description**: A creative and divergent thinker that explores connections, challenges assumptions, and discovers new possibilities using the DSRP framework.
*   **What it does**: Identifies and explores key distinctions present in a given topic, reflecting on how they shape understanding, introduce biases, and reveal or obscure insights.
*   **How to use it**:
    ```bash
    echo "The concept of 'freedom'" | fabric -p identify_dsrp_distinctions
    ```

---

### `identify_dsrp_perspectives`

*   **Description**: A creative and divergent thinker that explores connections, challenges assumptions, and discovers new possibilities using the DSRP framework.
*   **What it does**: Explores the key perspectives surrounding a system, considering the viewpoints of various stakeholders, how they influence the system, and what biases or assumptions are at play.
*   **How to use it**:
    ```bash
    echo "Analyzing the impact of social media on society" | fabric -p identify_dsrp_perspectives
    ```

---

### `identify_dsrp_relationships`

*   **Description**: A creative and divergent thinker that explores connections, challenges assumptions, and discovers new possibilities using the DSRP framework.
*   **What it does**: Explores the key relationships within a system, going beyond direct cause and effect to consider complex, indirect, and latent relationships, feedback loops, and dependencies.
*   **How to use it**:
    ```bash
    echo "The relationship between diet and health" | fabric -p identify_dsrp_relationships
    ```

---

### `identify_dsrp_systems`

*   **Description**: A creative and divergent thinker that explores connections, challenges assumptions, and discovers new possibilities using the DSRP framework.
*   **What it does**: Identifies and analyzes the systems and subsystems present in a given topic, considering their purpose, interactions, and connections to larger or external systems.
*   **How to use it**:
    ```bash
    echo "The education system" | fabric -p identify_dsrp_systems
    ```

---

### `identify_job_stories`

*   **Description**: A versatile and perceptive Job Story Generator.
*   **What it does**: Generates a diverse set of job stories based on a provided brief or scenario, capturing the needs, motivations, and desired outcomes of various stakeholders.
*   **How to use it**:
    ```bash
    echo "Scenario: Users want to manage their online subscriptions efficiently." | fabric -p identify_job_stories
    ```

---

### `improve_prompt`

*   **Description**: An expert LLM prompt writing service.
*   **What it does**: Takes an LLM/AI prompt as input and outputs a better version of the prompt using prompt writing expertise and knowledge from the provided documentation.
*   **How to use it**:
    ```bash
    cat old_prompt.txt | fabric -p improve_prompt
    ```

---

### `improve_report_finding`

*   **Description**: An extremely experienced 'jack-of-all-trades' cyber security consultant.
*   **What it does**: Takes a security finding from a penetration test report and outputs an improved report finding in markdown format, including a title, description, risk, recommendations, references, a one-sentence summary, and quotes.
*   **How to use it**:
    ```bash
    cat security_finding_draft.txt | fabric -p improve_report_finding
    ```

---

### `improve_writing`

*   **Description**: A writing expert.
*   **What it does**: Refines input text to enhance clarity, coherence, grammar, and style, and returns the improved text with no additional commentary.
*   **How to use it**:
    ```bash
    cat my_essay.txt | fabric -p improve_writing
    ```

---

### `judge_output`

*   **Description**: A Honeycomb query evaluator with advanced capabilities to judge if a query is good or not.
*   **What it does**: Takes a natural language query and a generated Honeycomb query as input, then writes a detailed critique explaining its reasoning and provides a pass/fail judgment.
*   **How to use it**:
    ```bash
    echo "NLQ: show me traces where ip is 10.0.2.90
    Query: {\"breakdowns\": [\"trace.trace_id\"], \"calculations\": [{\"op\": \"COUNT\"}], \"filters\": [{\"column\": \"net.host.ip\", \"op\": \"=\", \"value\": \"10.0.2.90\"}]}" | fabric -p judge_output
    ```

---

### `label_and_rate`

*   **Description**: An ultra-wise and brilliant classifier and judge of content.
*   **What it does**: Labels content with a comma-separated list of single-word labels and then gives it a quality rating (S, A, B, C, D Tier) and a score between 1 and 100.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p label_and_rate
    ```

---

### `md_callout`

*   **Description**: An ultra-wise and brilliant classifier and judge of content.
*   **What it does**: Creates a markdown callout based on the provided text, choosing the most appropriate callout type (Note, Tip, Important, Warning, Caution).
*   **How to use it**:
    ```bash
    echo "This is important information about the upcoming changes." | fabric -p md_callout
    ```

---

### `model_as_sherlock_freud`

*   **Description**: The Sherlock-Freud Mind Modeler, a fusion of meticulous detective reasoning and deep psychoanalytic insight.
*   **What it does**: Constructs a dynamic, evidence-based model of a subject’s psyche by analyzing their text or dialogue, providing a summary, behavioral clues, psychological interpretation, and a working theoretical model.
*   **How to use it**:
    ```bash
    cat subject_dialogue.txt | fabric -p model_as_sherlock_freud
    ```

---

### `official_pattern_template`

*   **Description**: A template for creating new Fabric patterns.
*   **What it does**: Provides a structured format for defining the identity, purpose, goals, steps, and output instructions for a new pattern.
*   **How to use it**:
    ```bash
    fabric -p official_pattern_template > new_pattern/system.md
    ```

---

### `predict_person_actions`

*   **Description**: An expert psychological analyst AI.
*   **What it does**: Assesses and predicts how an individual is likely to respond to a specific challenge based on their psychological profile and the challenging situation.
*   **How to use it**:
    ```bash
    cat psych_data.txt | fabric -p predict_person_actions
    ```

---

### `prepare_7s_strategy`

*   **Description**: A skilled business researcher preparing briefing notes that will inform strategic analysis.
*   **What it does**: Creates a comprehensive briefing document optimized for LLM processing that captures an organizational profile, strategic elements, and market dynamics using the 7S strategy framework.
*   **How to use it**:
    ```bash
    cat company_report.txt | fabric -p prepare_7s_strategy
    ```

---

### `provide_guidance`

*   **Description**: An all-knowing psychiatrist, psychologist, and life coach.
*   **What it does**: Provides honest and concise advice to people based on a question asked and context provided, including a one-sentence analysis, detailed analysis, recommendations, Esther Perel's advice, self-reflection questions, and possible clinical diagnoses.
*   **How to use it**:
    ```bash
    echo "I feel stuck in my career and don't know what to do." | fabric -p provide_guidance
    ```

---

### `rate_ai_response`

*   **Description**: An expert at rating the quality of AI responses.
*   **What it does**: Rates the quality of an AI's output compared to a human expert, assigning a letter grade, a score from 1-100, and providing reasons for the ratings.
*   **How to use it**:
    ```bash
    cat ai_instructions_and_output.txt | fabric -p rate_ai_response
    ```

---

### `rate_ai_result`

*   **Description**: An expert AI researcher and polymath scientist.
*   **What it does**: Assesses the quality of AI/ML/LLM work results, giving a numerical rating (1-100) and corresponding human-level execution level (Superhuman, World-class Human, etc.), along with deductions and improvements.
*   **How to use it**:
    ```bash
    cat ai_task_evaluation.txt | fabric -p rate_ai_result
    ```

---

### `rate_content`

*   **Description**: An ultra-wise and brilliant classifier and judge of content.
*   **What it does**: Labels content with a comma-separated list of single-word labels and then gives it a quality rating (S, A, B, C, D Tier) and a score between 1 and 100, focusing on human meaning and flourishing.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p rate_content
    ```

---

### `rate_value`

*   **Description**: An expert parser and rater of value in content.
*   **What it does**: Determines how much value a reader/listener is being provided in a given piece of content as measured by "Value Per Minute" (VPM).
*   **How to use it**:
    ```bash
    cat content_transcript.txt | fabric -p rate_value
    ```

---

### `raw_query`

*   **Description**: A universal AI that yields the best possible result given the input.
*   **What it does**: Fully digests and deeply contemplates the input and what it means, then outputs the best possible result based on the sender's likely intention.
*   **How to use it**:
    ```bash
    echo "Please summarize this document for me." | fabric -p raw_query
    ```

---

### `recommend_artists`

*   **Description**: An EDM expert who specializes in identifying artists I will like based on a list of artists at a festival.
*   **What it does**: Recommends a personalized festival schedule of artists based on preferred styles and artists, along with explanations.
*   **How to use it**:
    ```bash
    cat festival_lineup.txt | fabric -p recommend_artists
    ```

---

### `recommend_pipeline_upgrades`

*   **Description**: An ASI master security specialist specializing in optimizing how one checks for vulnerabilities in one's own systems.
*   **What it does**: Takes existing security pipelines and new information/wisdom, then optimizes the pipelines for efficiency, providing optimized versions and explanations of changes.
*   **How to use it**:
    ```bash
    cat current_pipelines.txt | fabric -p recommend_pipeline_upgrades
    ```

---

### `recommend_talkpanel_topics`

*   **Description**: An AI that reads a full input of a person and their goals and interests, and produces a clean set of proposed talks or panel talking points.
*   **What it does**: Brainstorms talk titles and abstracts, and panel topics with talking points, that can be sent directly to a conference organizer.
*   **How to use it**:
    ```bash
    cat speaker_profile.txt | fabric -p recommend_talkpanel_topics
    ```

---

### `refine_design_document`

*   **Description**: An expert in software, cloud, and cybersecurity architecture.
*   **What it does**: Refines a design document according to a provided design review, ensuring the changes are implemented using valid Markdown.
*   **How to use it**:
    ```bash
    cat design_document.md | fabric -p refine_design_document
    ```

---

### `review_code`

*   **Description**: A Principal Software Engineer, renowned for meticulous attention to detail and ability to provide clear, constructive, and educational code reviews.
*   **What it does**: Performs a comprehensive review of a code snippet or diff, generating a detailed report with overall assessment, prioritized recommendations, and detailed feedback for each issue.
*   **How to use it**:
    ```bash
    cat code.py | fabric -p review_code
    ```

---

### `review_design`

*   **Description**: An expert solution architect.
*   **What it does**: Conducts a detailed review of an architecture design, analyzing clarity, component design, external system integrations, security, performance, scalability, data management, and maintainability.
*   **How to use it**:
    ```bash
    cat architecture_design.md | fabric -p review_design
    ```

---

### `sanitize_broken_html_to_markdown`

*   **Description**: A hyper-intelligent AI system that converts jacked-up HTML to proper markdown.
*   **What it does**: Converts input HTML into a clean Markdown format with custom styling applied according to a set of rules, ensuring proper rendering with Vite.
*   **How to use it**:
    ```bash
    cat broken.html | fabric -p sanitize_broken_html_to_markdown
    ```

---

### `suggest_pattern`

*   **Description**: An expert AI assistant specialized in the Fabric framework.
*   **What it does**: Analyzes user requests and suggests the most appropriate Fabric patterns or commands to accomplish their goals, providing context and usage examples.
*   **How to use it**:
    ```bash
    echo "I want to summarize a long article." | fabric -p suggest_pattern
    ```

---

### `summarize`

*   **Description**: An expert content summarizer.
*   **What it does**: Takes content and outputs a Markdown formatted summary including a 20-word one-sentence summary, 10 main points, and 5 takeaways.
*   **How to use it**:
    ```bash
    cat article.txt | fabric -p summarize
    ```

---

### `summarize_board_meeting`

*   **Description**: A professional meeting secretary specializing in corporate governance documentation.
*   **What it does**: Converts raw board meeting transcripts into polished, formal meeting notes that meet corporate standards and legal requirements.
*   **How to use it**:
    ```bash
    cat board_meeting_transcript.txt | fabric -p summarize_board_meeting
    ```

---

### `summarize_debate`

*   **Description**: A hyper-intelligent ASI that excels at analyzing debates and/or discussions and determining the primary disagreement.
*   **What it does**: Provides a concise summary of where the participants are disagreeing, what arguments they're making, and what evidence each would accept to change their mind.
*   **How to use it**:
    ```bash
    cat debate_transcript.txt | fabric -p summarize_debate
    ```

---

### `summarize_git_changes`

*   **Description**: An expert project manager and developer, specializing in creating super clean updates for what changed a Github project in the last 7 days.
*   **What it does**: Reads the input (likely git logs or diffs) and summarizes the major changes and upgrades that happened in the last 7 days.
*   **How to use it**:
    ```bash
    git log --since="7 days ago" | fabric -p summarize_git_changes
    ```

---

### `summarize_git_diff`

*   **Description**: An expert project manager and developer, specializing in creating super clean updates for what changed in a Git diff.
*   **What it does**: Reads a git diff and outputs a concise commit message following conventional commits, along with a bulleted list of changes.
*   **How to use it**:
    ```bash
    git diff | fabric -p summarize_git_diff
    ```

---

### `summarize_lecture`

*   **Description**: An organized, high-skill expert lecturer.
*   **What it does**: Extracts the most relevant topics from a lecture transcript, provides a structured summary with bullet points and definitions, and includes timestamps.
*   **How to use it**:
    ```bash
    cat lecture_transcript.txt | fabric -p summarize_lecture
    ```

---

### `summarize_legislation`

*   **Description**: An expert AI specialized in reading and summarizing complex political proposals and legislation.
*   **What it does**: Summarizes the key points of a proposal, identifies tricky parts, and gives a holistic, unbiased view of its overall purpose and goals.
*   **How to use it**:
    ```bash
    cat legislation_text.txt | fabric -p summarize_legislation
    ```

---

### `summarize_meeting`

*   **Description**: An AI assistant specialized in analyzing meeting transcripts and extracting key information.
*   **What it does**: Provides comprehensive yet concise summaries of meetings in a structured format, capturing attendees, agenda items, discussion points, decisions, action items, and next steps.
*   **How to use it**:
    ```bash
    cat meeting_transcript.txt | fabric -p summarize_meeting
    ```

---

### `summarize_micro`

*   **Description**: An expert content summarizer.
*   **What it does**: Takes content and outputs a Markdown formatted summary including a 20-word one-sentence summary, 3 main points, and 3 takeaways.
*   **How to use it**:
    ```bash
    cat short_article.txt | fabric -p summarize_micro
    ```

---

### `summarize_newsletter`

*   **Description**: An advanced AI newsletter content extraction service.
*   **What it does**: Extracts the most meaningful, interesting, and useful content from an incoming newsletter, including a summary, opinions, tools, companies, and follow-up items.
*   **How to use it**:
    ```bash
    cat newsletter_content.txt | fabric -p summarize_newsletter
    ```

---

### `summarize_paper`

*   **Description**: An excellent academic paper reviewer.
*   **What it does**: Conducts paper summarization on the full paper text, providing title, authors, main goal, technical approach, distinctive features, experimental setup and results, advantages and limitations, and conclusion.
*   **How to use it**:
    ```bash
    cat academic_paper.txt | fabric -p summarize_paper
    ```

---

### `summarize_prompt`

*   **Description**: An expert prompt summarizer.
*   **What it does**: Takes AI chat prompts and outputs a concise summary of the purpose of the prompt, its nuanced approach, and its expected output.
*   **How to use it**:
    ```bash
    cat prompt_definition.txt | fabric -p summarize_prompt
    ```

---

### `summarize_pull-requests`

*   **Description**: An expert at summarizing pull requests to a given coding project.
*   **What it does**: Creates a one-sentence summary of pull request types and a bulleted list of the main PRs with human-readable descriptions.
*   **How to use it**:
    ```bash
    git log --oneline --grep="pull request" | fabric -p summarize_pull-requests
    ```

---

### `summarize_rpg_session`

*   **Description**: An expert summarizer of in-person role-playing game sessions.
*   **What it does**: Takes the transcript of a conversation and extracts the part about the RPG session, turning it into a detailed summary of key events, combat, character development, and narrative hooks.
*   **How to use it**:
    ```bash
    cat rpg_session_transcript.txt | fabric -p summarize_rpg_session
    ```

---

### `t_check_dunning_kruger`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Evaluates input against the Dunning-Kruger effect, exploring cognitive bias, subjective ability, and objective ability, and identifying areas of overestimation and underestimation of competence.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_check_dunning_kruger
    ```

---

### `t_check_metrics`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File, studies the input instruction, and checks the person's metrics or KPIs to determine their current state and recent improvements.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_check_metrics
    ```

---

### `t_create_h3_career`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction to think about what the person could and should do after their legacy corporate/technical skills are automated away, focusing on human-to-human interaction.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_create_h3_career
    ```

---

### `t_create_opening_sentences`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 4 32-word bullets describing who the person is, the problem they see in the world, and what they are doing about it.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_create_opening_sentences
    ```

---

### `t_describe_life_outlook`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 5 16-word bullets describing the person's life outlook.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_describe_life_outlook
    ```

---

### `t_extract_intro_sentences`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 5 16-word bullets describing who the person is, what they do, and what they're working on.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_extract_intro_sentences
    ```

---

### `t_extract_panel_topics`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 5 48-word bullet points, each including a 3-5 word panel title, that would be wonderful panels for this person to participate on.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_extract_panel_topics
    ```

---

### `t_find_blindspots`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 8 16-word bullets describing possible blindspots in the person's thinking.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_find_blindspots
    ```

---

### `t_find_negative_thinking`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 4 16-word bullets identifying negative thinking and adds tough love encouragement.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_find_negative_thinking
    ```

---

### `t_find_neglected_goals`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 5 16-word bullets describing which of their goals and/or projects don't seem to have been worked on recently.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_find_neglected_goals
    ```

---

### `t_give_encouragement`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 8 16-word bullets looking at what the person is trying to do, and any progress they've made, and gives encouragement.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_give_encouragement
    ```

---

### `t_red_team_thinking`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 4 16-word bullets red-teaming the person's thinking, models, frames, etc., and gives recommendations.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_red_team_thinking
    ```

---

### `t_threat_model_plans`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 8 16-word bullets threat modeling the person's life plan and what could go wrong, and provides recommendations.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_threat_model_plans
    ```

---

### `t_visualize_mission_goals_projects`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then creates an ASCII art diagram of the relationship between the person's missions, goals, and projects.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_visualize_mission_goals_projects
    ```

---

### `t_year_in_review`

*   **Description**: An AI that understands deep context about a person or entity, and then creates wisdom from that context.
*   **What it does**: Reads a TELOS File and the input instruction, then writes 8 16-word bullets describing what was accomplished this year and ends with an ASCII art visualization.
*   **How to use it**:
    ```bash
    cat telos_file.txt | fabric -p t_year_in_review
    ```

---

### `to_flashcards`

*   **Description**: A professional Anki card creator.
*   **What it does**: Extracts main points from the text and formulates questions and answers as Anki flashcards in CSV format, adhering to the minimum information principle and optimizing wording.
*   **How to use it**:
    ```bash
    cat study_text.txt | fabric -p to_flashcards > flashcards.csv
    ```

---

### `transcribe_minutes`

*   **Description**: An AI that extracts minutes from a transcribed meeting.
*   **What it does**: Identifies actionables, insightful ideas, decisions, challenges, and next steps from a meeting transcript, presenting them in a structured markdown format.
*   **How to use it**:
    ```bash
    cat meeting_transcript.txt | fabric -p transcribe_minutes
    ```

---

### `translate`

*   **Description**: An expert translator.
*   **What it does**: Translates sentences or documentation into the specified language code as accurately and perfectly as possible, maintaining the original format and tone.
*   **How to use it**:
    ```bash
    echo "Hello world" | fabric -p translate -v lang_code=es
    ```

---

### `tweet`

*   **Description**: An AI that provides a comprehensive guide to crafting engaging tweets with emojis.
*   **What it does**: Takes text as input and suggests how to turn it into an engaging tweet with emojis, based on best practices for Twitter.
*   **How to use it**:
    ```bash
    echo "This is a great article about AI ethics." | fabric -p tweet
    ```

---

### `write_essay_pg`

*   **Description**: An expert on writing concise, clear, and illuminating essays on the topic of the input provided.
*   **What it does**: Writes a full, publish-ready essay in the style of Paul Graham, known for his concise, clear, and simple style of writing.
*   **How to use it**:
    ```bash
    echo "The future of artificial intelligence" | fabric -p write_essay_pg
    ```

---

### `write_hackerone_report`

*   **Description**: An exceptionally talented bug bounty hunter that specializes in writing bug bounty reports that are concise, to-the-point, and easy to reproduce.
*   **What it does**: Takes HTTP requests and responses, along with a description of the attack flow, and generates a formatted HackerOne bug bounty report.
*   **How to use it**:
    ```bash
    cat bug_details.txt | fabric -p write_hackerone_report
    ```

---

### `write_latex`

*   **Description**: An expert at outputting syntactically correct LaTeX for a new .tex document.
*   **What it does**: Produces a well-formatted and well-written LaTeX file that will be rendered into a PDF for the user, based on their request.
*   **How to use it**:
    ```bash
    echo "A simple LaTeX document with a title and an author" | fabric -p write_latex
    ```

---

### `write_micro_essay`

*   **Description**: An expert on writing concise, clear, and illuminating essays on the topic of the input provided.
*   **What it does**: Writes a full, publish-ready micro-essay (maximum 250 words) on the topic of the input, in the style of Paul Graham.
*   **How to use it**:
    ```bash
    echo "The importance of focus in startups" | fabric -p write_micro_essay
    ```

---

### `write_nuclei_template_rule`

*   **Description**: An expert at writing YAML Nuclei templates.
*   **What it does**: Writes a Nuclei template that will match a provided vulnerability, incorporating elements like HTTP requests, matchers, extractors, and conditions.
*   **How to use it**:
    ```bash
    cat vulnerability_details.txt | fabric -p write_nuclei_template_rule
    ```

---

### `write_pull-request`

*   **Description**: An experienced software engineer about to open a PR.
*   **What it does**: Takes `git diff` output as input and drafts a detailed pull request description in markdown syntax, including a summary, files changed, code changes, reasons, impact, and test plan.
*   **How to use it**:
    ```bash
    git --no-pager diff main | fabric -p write_pull-request
    ```

---

### `write_semgrep_rule`

*   **Description**: An expert at writing Semgrep rules.
*   **What it does**: Writes a Semgrep rule that will match the input provided, catching any generic instance of the problem.
*   **How to use it**:
    ```bash
    cat code_snippet_with_vulnerability.txt | fabric -p write_semgrep_rule
    ```

---

### `youtube_summary`

*   **Description**: An AI assistant specialized in creating concise, informative summaries of YouTube video content based on transcripts.
*   **What it does**: Analyzes video transcripts, identifies key points, main themes, and significant moments, then organizes this information into a well-structured summary that includes relevant timestamps.
*   **How to use it**:
    ```bash
    cat youtube_transcript.txt | fabric -p youtube_summary
    ```

---

