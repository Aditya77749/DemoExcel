# AAVA Agent Generation Workflow - Knowledge Transfer Session

## Document Metadata
- **Session Date**: October 5, 2026
- **Session Time**: 08:32 AM
- **Session Type**: Knowledge Transfer - Agent Walkthrough
- **Facilitators**: Sowmya Sridhar, Kiruthika Ganesan, Aaditya Nayar
- **Attendees**: Ansiya Thangal Kunju, Mohan R, Hariharan Krishnaraj, Rajasowmya K
- **Application**: AAVA (AI-Assisted Agent Automation)
- **Module**: Agent Generation Workflow for Knowledge Transfer Automation

---

## Executive Summary

This knowledge transfer session covered the AAVA Agent Generation Workflow, a four-agent system designed to automate knowledge transfer documentation. The workflow processes input files (transcripts, PPTs, text files) and generates structured Markdown documentation with gap analysis, coverage metrics, and recommendations. The system integrates with GitHub for version control and knowledge base management.

**Key Capabilities:**
- Multi-format input processing (PPT, TXT, PDF, DOCX)
- Automated Markdown generation and GitHub upload
- Content summarization
- Domain file matching and retrieval
- Gap analysis with coverage scoring
- Knowledge transfer quality assessment

---

## Application Overview

### Purpose
The AAVA Agent Generation Workflow automates the knowledge transfer documentation process by:
1. Converting various input formats into standardized Markdown files
2. Generating comprehensive summaries
3. Performing gap analysis against existing domain documentation
4. Providing coverage metrics and recommendations

### Target Use Case
- **Primary**: Caresource healthcare domain knowledge transfer
- **Secondary**: General enterprise knowledge base automation
- **Scope**: Multi-tower application support with module-level documentation

---

## System Architecture

### Four-Agent Workflow

#### Agent 1: File Ingestion and MD Generation
**Function**: Input Processing and GitHub Upload
- **Input Formats**: Transcript files, PPT, TXT, PDF, DOCX
- **Processing**: Converts input to structured Markdown (.md) format
- **Output**: Uploads .md file to GitHub repository
- **Key Feature**: Dynamic content extraction and structuring

**Technical Details:**
- Accepts multiple file formats
- Extracts text content, tables, and structured data
- Generates clean Markdown syntax
- Commits to GitHub with automated folder structure (date-based)

#### Agent 2: Summarization
**Function**: Content Summary Generation
- **Input**: MD file from Agent 1
- **Processing**: Creates concise summary of key points
- **Output**: Summary uploaded to GitHub as separate file
- **Execution**: Mandatory (not conditional)

**Key Characteristics:**
- Runs for all inputs regardless of matching files
- Generates bullet-point summaries
- Preserves critical information
- Optimized for quick reference

#### Agent 3: Domain File Discovery and Content Retrieval
**Function**: GitHub Repository Analysis and File Matching
- **Process Flow**:
  1. Lists complete directory structure of GitHub repository
  2. Identifies domain-relevant files
  3. Performs similarity analysis
  4. Retrieves content from matching files
  5. Prepares data for gap analysis

**Technical Implementation:**
```
Sub-tasks:
1. Directory Listing: Fetch all files from GitHub repo
2. File Filtering: Select domain-relevant documents (2-3 files typically)
3. Content Retrieval: Read file contents
4. Similarity Analysis: Calculate match scores for File 1, File 2, File 3
```

**Output Example:**
- Lists all repository files
- Identifies 3 relatable files
- Performs content retrieval and similarity scoring
- Returns "No matching file found" if no domain match exists

#### Agent 4: Gap Analysis and Reporting
**Function**: Coverage Analysis and Gap Identification
- **Input**: 
  - Generated MD file (from Agent 1)
  - Domain file content (from Agent 3)
- **Processing**: Comparative analysis
- **Output**: Comprehensive gap analysis report

**Report Components:**
1. Coverage Score (percentage)
2. Coverage Matrix (Fully Covered, Partially Covered, Not Covered)
3. Gap Identification (High/Medium/Low priority)
4. Follow-up Questions
5. Recommendations
6. Detailed Topic Analysis

---

## Technical Implementation Details

### Input File Formats

#### Supported Formats
1. **PPT (PowerPoint Presentations)**
   - Status: Tested
   - Processing: Content extraction, slide-by-slide analysis
   
2. **TXT (Text Files)**
   - Status: Tested
   - Processing: Direct text ingestion

3. **Transcript Files**
   - Extension: `.tsi` (Microsoft-defined format, not `.txt`)
   - Source: Microsoft Teams recordings
   - Note: Must handle native transcript format without conversion

4. **PDF (Portable Document Format)**
   - Status: Supported with considerations
   - Challenges: 
     - Image extraction required
     - Table detection needed
     - Complex layout handling
   - Solution: JSON-based extraction and storage

5. **DOCX (Word Documents)**
   - Status: Accepted
   - Processing: Standard document parsing

#### PDF Processing Considerations
**Special Requirements:**
- Image detection and extraction
- Table structure preservation
- Multi-format content handling
- Recommended: Convert to JSON intermediate format before processing

**Implementation Note:**
```
PDF Processing Steps:
1. Detect content types (text, images, tables)
2. Extract each type separately
3. Store in JSON structure
4. Read and process from JSON
```

### GitHub Integration

#### Repository Structure
- **Organization**: Application-level folders
- **Date-based Folders**: Automatic YYYY-MM-DD structure
- **File Naming**: `<application-name>-knowledge-base.md`

#### Upload Process
1. Agent 1: Uploads input as .md file
2. Agent 2: Uploads summary file
3. Version Control: Automatic commit with descriptive messages
4. Access: GitHub Personal Access Token authentication

#### Repository Example
- Multiple files per application
- 2-3 domain-specific files per module
- Hierarchical organization for easy retrieval

---

## Gap Analysis Report Structure

### 1. Coverage Score
**Format**: Percentage (e.g., 92%)
**Calculation**: Based on topic matching between input and domain files

### 2. Coverage Matrix

| Topic | Criticality | Coverage Status | Transcript Evidence |
|-------|-------------|-----------------|---------------------|
| Token-based Model Extraction | High | Fully Covered | [Evidence details] |
| Authentication | Medium | Partially Covered | [Evidence details] |
| Technical Architecture | Medium | Partially Covered | [Evidence details] |

**Coverage Levels:**
- **Fully Covered**: Complete information present
- **Partially Covered**: Incomplete or missing details
- **Not Covered**: Topic not addressed

### 3. Gap Analysis

#### Gap Structure
Each gap includes:
- **Gap ID**: Sequential numbering
- **Category**: Technical Architecture, Implementation, etc.
- **Priority**: High/Medium/Low
- **Current State**: What was covered in the session
- **Specific Gap**: What is missing
- **Risk Assessment**: Using RAID framework
  - **R**isk
  - **A**ssumption
  - **I**ssue
  - **D**ependency

**Example Gap:**
```
Gap 1: Technical Architecture - Technology Stack Mapping
- Priority: Medium
- Current State: Session covered Python-based automation
- Specific Gap: Technologies not explicitly mapped to architecture
- Risk: Operational risk (medium)
- Follow-up: Provide detailed technology stack mapping
```

### 4. Risk Assessment Framework

#### RAID Methodology
**Recommended Approach**: Use RAID for comprehensive risk analysis

**Components:**
- **Risk**: Potential issues and their impact
- **Assumption**: Dependencies on unverified conditions
- **Issue**: Current problems requiring resolution
- **Dependency**: External factors affecting implementation

**Risk Categories:**
- Technical Risk
- Operational Risk
- Business Risk

### 5. Criticality Levels

#### Recommended Classification
**Three-tier System**: High, Medium, Low

**Rationale**: 
- Avoids ambiguity of two-tier (High/Medium) systems
- Provides clear differentiation
- Enables better prioritization

**Alternative**: Use average/aggregate scoring instead of binary classification

### 6. Follow-up Questions
- Specific queries for clarification
- Action items for knowledge gaps
- Technical details requiring elaboration

### 7. Recommendations
**Format**: Bullet points for clarity
- Immediate actions
- Medium-term improvements
- Long-term enhancements

### 8. Detailed Topic Analysis

#### Fully Covered Topics
- Core pipeline workflow
- System objectives
- GitHub uploader tool configuration

#### Partially Covered Topics
- Component diagrams (missing Python version specifics)
- Technology stack details
- Architecture layer mapping

#### Not Covered Topics
- [Listed based on domain file comparison]

---

## Report Formatting Guidelines

### Transcript Evidence Section
**Current Approach**: Direct quotes from transcript
**Recommended Enhancement**: AI-summarized evidence
- Use Microsoft Teams AI summary format
- Maintain meaning while shortening content
- Convert to active voice (not passive)
- Create bullet-point summaries

**Example Transformation:**
```
Before (Verbose):
"The knowledge base automation pipeline implemented a three-stage workflow 
consisting of file integration, dynamic extraction, and Github synchronization 
with complete details breakdown provided with subprocess..."

After (Concise):
"Three-stage workflow: file integration → dynamic extraction → GitHub sync"
```

### Section Naming Conventions
**Improvements Suggested:**
- "Specific Gap" → "Identified Gap"
- "All Fully Covered" → "Fully Covered" or "Covered"
- Remove "No action required" statements
- Replace with "Action Priority: Low"

### Content Organization
**Recommended Structure:**
1. Executive Summary (bullet points)
2. Coverage Matrix (table format)
3. Gap Analysis (structured sections)
4. Recommendations (bullet points)
5. Conclusion (brief paragraph)

**Remove/Consolidate:**
- Knowledge Transfer Quality Assessment (redundant)
- Duplicate summary sections
- Agent-generated judgments ("no action required")

---

## LLM Configuration

### Current Setup
- **Model**: Claude (Anthropic)
- **Platform**: AAVA (AI-Assisted Agent Automation)
- **Alternative**: ChatGPT (OpenAI)

### Agent Prompting
**Current State**: General instructions without strict rubrics
**Recommendation**: Develop formal rubrics for:
- Coverage scoring methodology
- Gap prioritization criteria
- Risk assessment guidelines
- Output formatting standards

---

## Testing and Validation

### Test Inputs Used
1. **PPT File**: Agent workflow presentation
2. **Transcript File**: Dummy meeting transcript
3. **Content Scope**: Knowledge base automation pipeline

### Test Results
- **Coverage Score**: 92%
- **Gaps Identified**: 2 medium priority, 1 low priority
- **File Matching**: 3 relevant domain files found
- **Summary Generation**: Successful

### Limitations Identified
1. **Content Complexity**: Test data less complex than healthcare domain
2. **Image Handling**: Not fully implemented for PDFs
3. **Rubrics**: Need formal scoring criteria
4. **Format Standardization**: Requires client KT document templates

---

## Integration with Caresource

### Requirements
1. **Domain Specificity**: Healthcare-focused content
2. **Multiple Towers**: Support for various application modules
3. **KT Document Format**: Need existing templates from client
4. **Screenshot Handling**: Application UI captures in documentation

### Challenges
1. **No Existing Documentation**: Some towers starting fresh
2. **Complex Domain**: Healthcare terminology and workflows
3. **Multi-session KT**: Consolidation of multiple sessions required
4. **Image Content**: Screenshots not captured in transcripts

### Proposed Solutions

#### Workflow 1: Single Session Processing (Current)
- Process individual KT session
- Generate MD file and summary
- Perform gap analysis
- Upload to GitHub

#### Workflow 2: Multi-session Consolidation (Future)
**Purpose**: Create comprehensive KT document from multiple sessions

**Process:**
1. Identify all MD files for specific application/module
2. Read content from all session files
3. Consolidate into single comprehensive document
4. Follow client KT document format
5. Generate final application-level KT document

**Example Scenario:**
```
Claims Module KT:
- Session 1: Claims Creation (MD file 1)
- Session 2: Claims Adjudication (MD file 2)
- Session 3: Claims Settlement (MD file 3)
- Session 4: Claims Reporting (MD file 4)
→ Consolidated: Claims Module Complete KT Document
```

---

## Future Enhancements

### 1. Video/Audio to Text Conversion
**Requirement**: Process KT recordings without transcripts
**Status**: Not currently implemented
**Action**: Check with Lata's team for existing solutions
**Use Case**: Startup team with multiple recordings lacking transcripts

### 2. Image and Diagram Handling
**Requirements:**
- Screenshot extraction from PDFs
- Workflow diagram generation
- Architecture diagram inclusion
- Application UI captures

**Technical Approach:**
- Base64 encoding for images
- Image-to-text conversion using AI
- Diagram generation from text descriptions
- Manual screenshot insertion workflow

**Reference**: Jira contextualization project (image handling code available)

### 3. Excel File Support
**Requirement**: Process Excel-based documentation
**Status**: Under consideration
**Use Case**: SSML agent content reading

### 4. Structured Output Format
**Requirement**: Client-specific KT document templates
**Action Items:**
- Obtain Caresource KT document samples
- Develop rubrics based on client format
- Train agents with structured templates
- Validate output against standards

### 5. Microsoft Copilot Integration
**Status**: Parallel development track
**Rationale**: 
- Caresource RFP may prefer Copilot over AAVA
- M365 integration benefits
- Easier implementation for certain features

**Decision Pending**: AAVA vs. Copilot for final deployment

---

## Implementation Recommendations

### Immediate Actions (High Priority)

1. **Implement RAID Framework**
   - Update risk assessment methodology
   - Add RAID columns to gap analysis
   - Include gap identification in risk table

2. **Refine Criticality Levels**
   - Adopt three-tier system (High/Medium/Low)
   - Define clear criteria for each level
   - Apply consistently across all gaps

3. **Enhance Transcript Evidence**
   - Implement AI summarization
   - Convert to active voice
   - Create concise bullet points

4. **Update Section Naming**
   - "Identified Gap" instead of "Specific Gap"
   - "Fully Covered" instead of "All Fully Covered"
   - Remove agent judgments on actions

5. **Format Summary Section**
   - Convert to bullet points
   - Remove redundant paragraphs
   - Maintain executive summary style

### Medium-Term Actions

1. **Obtain Client Templates**
   - Contact Radhika for Caresource KT documents
   - Review existing format standards
   - Develop rubrics based on templates

2. **Enhance PDF Processing**
   - Implement image extraction
   - Add table detection
   - Create JSON intermediate format

3. **Support Native Transcript Format**
   - Handle `.tsi` extension
   - Avoid TXT conversion
   - Process large transcripts efficiently

4. **Remove Redundant Sections**
   - Eliminate "Knowledge Transfer Quality Assessment"
   - Consolidate duplicate summaries
   - Streamline report structure

### Long-Term Actions

1. **Multi-session Consolidation Workflow**
   - Design Workflow 2 architecture
   - Implement MD file aggregation
   - Create comprehensive document generator

2. **Video/Audio Processing**
   - Explore conversion solutions
   - Integrate with existing agents
   - Test with actual KT recordings

3. **Image and Diagram Support**
   - Implement screenshot handling
   - Add diagram generation
   - Support manual image insertion

4. **Platform Decision**
   - Evaluate AAVA vs. Copilot
   - Consider client preferences
   - Plan migration if needed

---

## Key Decisions and Action Items

### Decisions Made
1. ✅ Four-agent workflow architecture approved
2. ✅ GitHub as primary storage repository
3. ✅ Mandatory summary generation for all inputs
4. ✅ RAID framework for risk assessment
5. ✅ Three-tier criticality system (High/Medium/Low)

### Action Items

| Item | Owner | Priority | Status |
|------|-------|----------|--------|
| Implement RAID framework in gap analysis | Development Team | High | Pending |
| Update criticality classification to 3-tier | Development Team | High | Pending |
| Enhance transcript evidence with AI summary | Development Team | Medium | Pending |
| Obtain Caresource KT document templates | Hariharan/Radhika | High | In Progress |
| Refine section naming conventions | Development Team | Medium | Pending |
| Remove "Knowledge Transfer Quality Assessment" | Development Team | Low | Pending |
| Format summary as bullet points | Development Team | Medium | Pending |
| Research video-to-text conversion | Hariharan/Lata's Team | Medium | Pending |
| Implement PDF image extraction | Development Team | Medium | Pending |
| Support native transcript format (.tsi) | Development Team | High | Pending |
| Design multi-session consolidation workflow | Architecture Team | Medium | Pending |
| Evaluate Copilot vs AAVA for deployment | Leadership | High | In Progress |

### Follow-up Questions
1. What is the exact transcript file extension from Microsoft Teams?
2. Can Radhika provide sample Caresource KT documents?
3. Does Lata's team have video-to-text conversion agents?
4. What is the final platform decision: AAVA or Copilot?
5. Are there existing rubrics for KT document quality assessment?

---

## Technical Specifications

### GitHub Configuration
- **Repository Owner**: Configurable
- **Repository Name**: Configurable
- **Branch**: main (default)
- **Authentication**: Personal Access Token
- **Folder Structure**: Date-based (YYYY-MM-DD)
- **File Naming**: `<application>-knowledge-base.md`

### Agent Configuration
- **Agent 1**: File Ingestion and MD Generation
- **Agent 2**: Summarization
- **Agent 3**: Domain File Discovery
- **Agent 4**: Gap Analysis and Reporting

### LLM Settings
- **Primary Model**: Claude (Anthropic)
- **Alternative**: ChatGPT (OpenAI)
- **Platform**: AAVA / Microsoft Copilot (under evaluation)

---

## Glossary

- **AAVA**: AI-Assisted Agent Automation
- **KT**: Knowledge Transfer
- **MD**: Markdown
- **RAID**: Risk, Assumption, Issue, Dependency
- **RAG**: Retrieval-Augmented Generation
- **PPT**: PowerPoint Presentation
- **PDF**: Portable Document Format
- **LLM**: Large Language Model
- **M365**: Microsoft 365
- **Copilot**: Microsoft Copilot

---

## References and Resources

### Related Projects
- **Jira Contextualization**: Image handling and Base64 encoding
- **Essilor Project**: PDF content reading implementation
- **SSML Agent**: Excel file processing

### Team Contacts
- **Sowmya Sridhar**: Lead Developer
- **Kiruthika Ganesan**: Developer
- **Aaditya Nayar**: Developer
- **Ansiya Thangal Kunju**: Project Coordinator
- **Mohan R**: Technical Reviewer
- **Hariharan Krishnaraj**: Domain Expert
- **Rajasowmya K**: Business Analyst

### External Stakeholders
- **Radhika**: Caresource KT Document Owner
- **Rishikesh**: Caresource Account Team
- **Nidhi**: Document Repository Contact
- **Lata's Team**: AI/ML Specialists
- **Vijay**: Leadership/Decision Maker

---

## Appendix

### Sample Output Structure

```markdown
# Knowledge Transfer Coverage Analysis Report

## Coverage Score: 92%

## Coverage Matrix
| Topic | Criticality | Coverage Status | Transcript Evidence |
|-------|-------------|-----------------|---------------------|
| Core Pipeline Workflow | High | Fully Covered | Three-stage workflow implemented |
| Token-based Model | High | Fully Covered | Authentication mechanism discussed |
| Technical Architecture | Medium | Partially Covered | Python stack mentioned, details missing |

## Gap Analysis

### Gap 1: Technical Architecture - Technology Stack Mapping
- **Priority**: Medium
- **Current State**: Python-based automation discussed
- **Identified Gap**: Technology stack not mapped to architecture layers
- **Risk Assessment (RAID)**:
  - Risk: Operational (Medium)
  - Assumption: Standard Python libraries used
  - Issue: None currently
  - Dependency: Architecture documentation
- **Follow-up**: Provide detailed technology stack with version specifics

### Gap 2: [Additional gaps...]

## Recommendations
- Immediate: Document technology stack with versions
- Medium-term: Create architecture layer diagrams
- Long-term: Establish documentation standards

## Summary
- Knowledge transfer session achieved 92% coverage
- 2 medium-priority gaps identified
- Follow-up sessions recommended for complete coverage
```

---

## Document Control

- **Version**: 1.0
- **Created**: October 5, 2026
- **Last Updated**: October 5, 2026
- **Document Owner**: AAVA Development Team
- **Review Cycle**: After each KT session
- **Classification**: Internal Use

---

## Notes

This knowledge base document was generated from a live knowledge transfer session and represents the current state of the AAVA Agent Generation Workflow. The system is under active development, and enhancements are being implemented based on stakeholder feedback and client requirements.

For questions or clarifications, please contact the AAVA development team or refer to the GitHub repository for the latest code and documentation updates.