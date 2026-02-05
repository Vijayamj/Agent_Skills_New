---
name: creating-resumes
description: Generates professional, tailored resumes focusing on personal details, work experience, education, and technical skills. Use when the user wants to build, update, or optimize their CV/Resume for job applications.
---
# Resume Creator

This skill helps users build high-impact resumes with a focus on ATS optimization and professional formatting.

## When to use this skill
- User says "Help me create/update my resume".
- User provides job history and asks for a CV.
- User wants to optimize their "Technical Skills" or "Experience" section.

## Workflow
1. [ ] **Information Gathering**: Collect the following details:
    - **Personal Details**: Name, Contact, LinkedIn/GitHub URL.
    - **Experience**: Job titles, companies, dates, and key achievements (bullet points).
    - **Education**: Degree, Institution, Graduation date.
    - **Technical Skills**: Programming languages, tools, frameworks, and methodologies.
2. [ ] **Template Selection**: Use the [Modern Resume Template](resources/resume-template.md).
3. [ ] **Content Optimization**: 
    - Convert passive sentences to active "Action-Result" patterns (e.g., "Led testing" -> "Increased test coverage by 40% using Playwright").
    - Ensure keyword density for ATS (Applicant Tracking Systems).
4. [ ] **Drafting**: Generate the resume in Markdown format.
5. [ ] **Review**: Ask for feedback and refine specific sections.

## Instructions

### 1. Achievement Pattern
Use the **Context-Action-Result (CAR)** method for the experience section:
- *Bad*: "Responsible for automation."
- *Good*: "Reduced regression time by 60% (Result) by implementing a Playwright POM framework (Action) for the VWO login module (Context)."

### 2. Skill Categorization
Do not just provide a list of strings. Categorize them:
- **Languages**: TS, JS, Java, Python.
- **Frameworks**: Playwright, Selenium, React.
- **Tools/DevOps**: Git, Docker, JIRA, Jenkins.

## Resources
- [Modern Resume Template](resources/resume-template.md)
- [Example Resume](examples/sample-resume.md)
